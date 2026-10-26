# Ninja Hangman

Ninja Hangman è un gioco mobile multiplayer per Android e iOS, sviluppato con C# e .NET MAUI. Il progetto prende ispirazione dal classico gioco dell'impiccato e usa una mascotte ninja originale come riferimento visivo.

## Stato del progetto

**Fase corrente: M0 — Fondamenta e specifiche.**

Il repository contiene lo scheletro multipiattaforma generato da Visual Studio. Le regole complete del gioco e l'interfaccia personalizzata non sono ancora implementate.

## Visione

Offrire partite brevi, immediate e divertenti tra due giocatori, con grafica cartoon, una mascotte riconoscibile e sfide in tempo reale.

## Piattaforme e tecnologie

- Client mobile: C# / .NET MAUI
- Target: Android e iOS
- Backend candidato: Supabase, da validare con un prototipo tecnico
- IDE principale: Visual Studio su Windows
- Build e firma iOS: ambiente macOS compatibile con le versioni .NET/Xcode adottate

## MVP pianificato

1. Motore di gioco locale con regole testate.
2. Interfaccia mobile e mascotte.
3. Backend autorevole e sincronizzazione in tempo reale.
4. Invito tramite codice e matchmaking casuale.
5. Test beta su Android e iOS.

Le funzionalità non essenziali (classifiche globali, chat libera, negozio, tornei e partite asincrone) sono fuori dal primo MVP.

## Regole iniziali proposte — da confermare

- Due round per partita: ogni giocatore sceglie una parola e l'avversario tenta di indovinarla.
- Una lettera per tentativo; niente suggerimenti nella modalità classica.
- Il server convalida le mosse e mantiene segreta la parola.
- Limite di errori, timer e lingue disponibili devono essere confermati prima di M1.

## Documentazione

- [Visione e requisiti MVP](docs/PROJECT.md)
- [Architettura](docs/ARCHITECTURE.md)
- [Roadmap](docs/ROADMAP.md)
- [Registro decisioni](docs/DECISIONS.md)
- [Report di sessione](docs/SESSION_REPORT.md)

## Metodo di lavoro

Le modifiche sono suddivise in milestone con criteri di accettazione verificabili. Nessuna dipendenza backend o feature aggiuntiva viene introdotta prima che il relativo obiettivo sia approvato.

## Nota sulla reference grafica

La mascotte fornita dal proprietario del progetto è il riferimento visivo da rispettare. L'immagine originale e i relativi diritti/licenze devono essere custoditi e documentati dal proprietario prima di includere gli asset nel repository pubblico.
