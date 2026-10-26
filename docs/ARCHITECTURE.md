# Ninja Hangman — Architettura iniziale

**Stato:** proposta da validare con un prototipo tecnico.

## Principi
1. Separare le regole del gioco dall'interfaccia MAUI.
2. Il server è l'autorità per le partite multiplayer.
3. Tenere la parola segreta sul server e inviare al client solo lo stato necessario.
4. Usare gli eventi realtime come notifiche, non come unica fonte dello stato.
5. Ridurre le dipendenze finché il motore locale non è verificato.
6. Ogni SDK/backend va introdotto solo dopo un caso d'uso e un test.

## Componenti previsti
- **MAUI:** schermate, navigazione, input, animazioni e accessibilità.
- **Game domain:** regole C# indipendenti da MAUI e dalla rete.
- **Application services:** orchestrazione dei casi d'uso.
- **Infrastructure adapters:** integrazioni backend e persistenza.

La struttura finale di progetti/assembly sarà decisa dopo aver verificato la soluzione di Visual Studio; evitare refactor massivi non necessari.

## Backend candidato
Supabase è candidato per PostgreSQL, autenticazione e realtime. Compatibilità .NET, SDK, funzioni server e modello di sicurezza vanno verificati con un prototipo prima di fissare la dipendenza.

Operazioni server previste: creare/accettare una partita, entrare in coda casuale, impostare parola, inviare lettera, recuperare stato dopo riconnessione, abbandonare/chiudere partita. La parola segreta non deve essere disponibile con query diretta dalle tabelle client.

## Flusso di una mossa
1. Il client invia un comando con ID partita, ID univoco richiesta e lettera.
2. Il server verifica identità, partecipazione, stato, turno, formato e duplicati.
3. Il server applica la regola in modo atomico e registra lo stato.
4. Il server restituisce lo stato ridotto e pubblica l'aggiornamento ai partecipanti autorizzati.
5. Il client aggiorna la UI; dopo un evento perso o reconnect, ricarica lo stato autorevole.

Le lettere provate possono essere visibili a entrambi; la parola segreta e dati che la ricostruiscano restano riservati.

## Modello dati concettuale
- **Profile:** user ID, nickname, avatar opzionale.
- **Match:** ID, modalità, stato, giocatori, round corrente, timestamp e timeout.
- **Round:** partita, numero round, setter, guesser, parola protetta lato server, lettere provate, errori, stato e risultato.
- **Move:** ID/idempotency key, round, giocatore, lettera, esito, timestamp e sequenza.

È un modello concettuale, non lo schema SQL definitivo.

## Sicurezza
- Nessuna lettura client della parola segreta.
- Ogni operazione verifica appartenenza e ruolo/turno.
- RLS e permessi database testati con utenti distinti.
- Operazioni critiche atomiche e protette da concorrenza.
- Nessuna service-role key o segreto backend nell'app.
- Rate limiting e anti-abuso definiti prima della beta pubblica.

## Realtime
Il realtime notifica i cambiamenti; la correttezza non dipende dalla consegna di ogni evento. Dopo reconnect/eventi persi il client ricarica lo stato autorevole. Prima di selezionare Broadcast/Presence o alternative, testare autenticazione canali, privacy stanza, reconnect e isolamento tra partite.

## Build
- Sviluppo primario: Visual Studio su Windows.
- Android: emulatori e device fisici.
- iOS: host macOS remoto compatibile con le versioni .NET/Xcode scelte.
- Verificare SDK, workload MAUI, target framework e firma prima della beta.

## Osservabilità
Non registrare parole segrete o contenuti sensibili nei log. Registrare solo identificatori, esiti, errori tecnici e tempi utili alla diagnosi.

## Decisioni aperte
Backend/SDK finale, autenticazione MVP, timer e abbandono, matchmaking, schema DB, gestione vocabolario, animazioni e formato asset.
