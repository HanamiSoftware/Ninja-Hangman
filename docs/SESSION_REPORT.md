# Ninja Hangman — Report di sessione

**Data:** 2026-10-26  
**Sessione:** bootstrap progetto

## Lavoro svolto
- Verificato il repository pubblico HanamiSoftware/Ninja-Hangman.
- Confermato lo scheletro multipiattaforma generato da Visual Studio.
- Rilevati `Ninja Hangman.slnx`, progetto condiviso `Ninja Hangman` e progetti `Ninja Hangman.Droid` e `Ninja Hangman.iOS`.
- Il progetto condiviso dichiara `net10.0`, `UseMaui=true`, nullable abilitato e XAML source generation.
- La schermata iniziale contiene ancora il template standard Hello World e un contatore.
- Aggiunte prime bozze di README, requisiti, architettura, roadmap e decision log.

## Cosa non è stato fatto
- Nessun codice C# o XAML esistente modificato.
- Non è stata eseguita una build: questa sessione non ha accesso all'ambiente Visual Studio locale.
- Supabase non è stato verificato con prototipo.
- Regole aperte (timer, errori, lingue, punteggio) non sono state decise.
- Nessun asset della mascotte aggiunto.

## Rischi e note
- Il repository è pubblico: non committare chiavi, token, certificati, provisioning profile o credenziali.
- `LICENSE.txt` contiene i placeholder `[year]` e `[fullname]`; completarlo con i dati corretti prima di considerare definita la licenza.
- Aggiungere gli asset della designer solo dopo aver chiarito diritti, sorgenti e varianti.
- Il backend resta candidato, non una dipendenza acquisita.

## Prossimi passi
1. Il proprietario conferma timer, errori massimi, lingue e policy parole.
2. Eseguire una build pulita in Visual Studio e registrare avvisi/errori.
3. Correggere licenza e convenzioni repository.
4. Definire motore locale e casi di test.
5. Iniziare M1 dopo approvazione dei criteri.
