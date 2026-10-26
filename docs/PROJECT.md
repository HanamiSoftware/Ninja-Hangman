# Ninja Hangman — Visione e requisiti MVP

**Stato:** bozza iniziale da approvare  
**Piattaforme:** Android e iOS  
**Client:** C# / .NET MAUI  
**Modalità MVP:** multiplayer in tempo reale  
**Identità visiva:** mascotte ninja originale fornita dal proprietario del progetto

## Obiettivo
Realizzare un gioco mobile multiplayer di parole, immediato da capire e con una direzione artistica cartoon riconoscibile. Due giocatori affrontano round alternati: ciascuno sceglie una parola che l'altro deve indovinare.

## Modalità MVP
- **Sfida con un amico:** creare una stanza e condividere un codice o link d'invito.
- **Sfida casuale:** entrare in coda ed essere abbinati a un giocatore disponibile.
- Le partite sono in tempo reale; le partite asincrone sono fuori scope.

## Flusso di partita proposto
1. Un giocatore crea o accetta una sfida.
2. La partita attende entrambi i giocatori.
3. A imposta una parola segreta; B la indovina.
4. Il round termina quando la parola è indovinata o viene raggiunto il limite di errori.
5. I ruoli si invertono.
6. Il server determina e comunica il risultato finale.

## Regole da confermare
- Lingue al lancio: italiano oppure italiano e inglese.
- Lunghezza minima/massima della parola.
- Numero massimo di errori per round.
- Timer assente oppure tempo per lettera/turno.
- Trattamento di accenti, spazi, apostrofi, trattini e caratteri non alfabetici.
- Parole offensive, nomi propri e parole improprie.
- Punteggio e gestione del pareggio.
- Abbandono, timeout e perdita connessione.
- Se la parola può essere cambiata prima del round.

## Requisiti funzionali MVP
- **FR-01 Avvio partita:** sfida con amico o casuale.
- **FR-02 Creazione parola:** il giocatore imposta la parola; il server applica la validazione autorevole.
- **FR-03 Tentativi:** una lettera valida per tentativo; lettere già provate non consumano tentativi.
- **FR-04 Stato round:** mostrare slot parola, lettere provate, errori rimasti e stato partita.
- **FR-05 Risultato round:** terminazione deterministica per vittoria o esaurimento errori.
- **FR-06 Round alternati:** invertire i ruoli dopo il primo round.
- **FR-07 Stato condiviso:** entrambi i client ricevono aggiornamenti e vedono lo stato autorevole.
- **FR-08 Recupero:** dopo disconnessione temporanea, ricaricare lo stato senza duplicare mosse.
- **FR-09 Autorizzazione:** leggere/modificare solo partite per cui l'utente è autorizzato.

## Requisiti non funzionali
- La parola segreta non viene inviata all'avversario prima della fine del round.
- Il server valida le mosse, conta gli errori e determina il risultato.
- Le richieste sono idempotenti o hanno un ID univoco per evitare duplicazioni.
- Nessuna credenziale backend privata nel client.
- Errori di rete comunicati in modo comprensibile.
- UI adattabile a differenti schermi e aree sicure.
- Motore testabile senza avviare MAUI né connettersi al backend.

## Direzione visiva
La reference della designer mostra un ninja stilizzato con rosso intenso, nero e bianco, forme semplici e contorni marcati. È il riferimento da rispettare, non un'autorizzazione a ridisegnare arbitrariamente il personaggio. Le animazioni avanzate richiederanno asset separati o pose/espressioni concordate con la designer.

## Fuori scope MVP
Chat libera, tornei, classifiche globali, negozio/valuta, molte mascotte, partite asincrone, social graph completo e bot.

## Criteri di uscita MVP
- Due dispositivi completano entrambi i round.
- Modalità amico e casuale funzionanti.
- Tentativi invalidi/ripetuti non alterano lo stato.
- Parola segreta non esposta all'avversario.
- Riconnessione e abbandono hanno esiti definiti.
- Test automatici del motore e dei flussi server passano.
- Verifica su Android e iOS reali.
- Sicurezza e autorizzazioni verificate prima di invitare utenti esterni.
