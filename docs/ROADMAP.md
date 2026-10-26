# Ninja Hangman — Roadmap

**Ultimo aggiornamento:** 2026-10-26  
**Milestone corrente:** M0 — Fondamenta e specifiche

Nessun task di implementazione parte finché decisioni e criteri di accettazione necessari non sono chiari e approvati.

## M0 — Fondamenta e specifiche (in corso)
- [x] Verificato lo scheletro MAUI nel repository.
- [x] Aggiunte prime bozze di visione, architettura e roadmap.
- [ ] Confermare timer, errori massimi, lingue, punteggio e casi limite.
- [ ] Verificare build pulita della soluzione in Visual Studio.
- [ ] Confermare convenzioni branch/review.
- [ ] Definire proprietà e licenza degli asset della designer.

**Uscita:** MVP approvato e ambiente riproducibile.

## M1 — Motore locale (non iniziata)
- [ ] Implementare dominio C# indipendente da MAUI.
- [ ] Definire stati round e transizioni valide.
- [ ] Gestire lettera, duplicati, vittoria e sconfitta.
- [ ] Specificare normalizzazione Unicode/accenti.
- [ ] Test automatici per casi normali e limite.
- [ ] Schermata essenziale per provare il round end-to-end.

**Accettazione:** dominio senza dipendenze MAUI/rete; input invalidi/ripetuti non consumano tentativi; esiti deterministici; test verdi; prototipo Android senza regressioni.

## M2 — UI e identità visiva (non iniziata)
- [ ] Home con azioni principali.
- [ ] Round con slot parola, tastiera e contatore errori.
- [ ] Integrare asset autorizzati della mascotte.
- [ ] Feedback accessibile per successo, errore e fine round.
- [ ] Layout adattabile.

**Accettazione:** flusso locale usabile senza backend, testo leggibile e controlli accessibili.

## M3 — Backend e multiplayer (non iniziata)
- [ ] Validare backend e SDK con prototipo minimo.
- [ ] Implementare identità e autorizzazioni.
- [ ] Creare partita/round lato server.
- [ ] Proteggere parola segreta.
- [ ] Mosse atomiche e idempotenti.
- [ ] Sincronizzare due client.
- [ ] Testare reconnect, eventi persi e richieste concorrenti.

**Accettazione:** due client completano una partita senza rivelare la parola e senza divergenza di stato.

## M4 — Inviti e matchmaking (non iniziata)
- [ ] Invito tramite codice/link.
- [ ] Coda casuale e abbinamento atomico.
- [ ] Cancellazione/timeout coda.
- [ ] Definizione di abbandono, timeout e riconnessione.
- [ ] Prevenire partite duplicate.

**Accettazione:** entrambe le modalità funzionano e i casi d'errore hanno esiti documentati.

## M5 — Beta e rilascio (non iniziata)
- [ ] Build Android di test.
- [ ] Build iOS firmata e TestFlight.
- [ ] Test su device reali.
- [ ] Checklist privacy, sicurezza, crash e rete.
- [ ] Raccolta feedback e triage bug.
- [ ] Listing store e policy.

**Accettazione:** flusso end-to-end verificato; bug bloccanti risolti; scope controllato.

## M6 — Dopo MVP
Solo dopo la beta: statistiche, classifiche/leghe, personalizzazioni, altre lingue, partite asincrone ed eventuali acquisti.
