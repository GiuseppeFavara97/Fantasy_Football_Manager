# Fantasy Football Manager

## Descrizione
Fantasy Football Manager è un'applicazione che permette agli utenti di gestire la propria squadra di calcio in un campionato fantasy. 
Il programma deve contenere almeno le seguent entità:
  - User: con id, username, email e password. Ruolo (USER, ADMIN), per distinguere amministratori e utenti.
  - Player: id, name, position, team, value (valore del giocatore), points (punteggio accumulato basato su performance reali).
  - FantasyTeam: id, teamName, user (relazione con User), players (relazione con Player), totalPoints.
  - League: id, name, teams (relazione con FantasyTeam).
  - Match (Partita reale): id, homeTeam, awayTeam, date, score.

##Fuzionalità  

- Registrazione e Login (Spring Security + JWT)
    Autenticazione con email e password.
    JWT per gestire sessioni sicure.
    Registrazione con ruoli (gli admin potrebbero aggiungere nuovi giocatori o gestire la lega).
- Gestione dei Giocatori
    CRUD per gestire i giocatori nel sistema.
    Possibilità di inserire dati manualmente o integrarli con API di terze parti (ad esempio, API di statistiche sportive).
    Ogni giocatore avrà un punteggio legato alle sue performance reali.
- Creazione e Gestione di Squadre Fantasy
    Gli utenti possono creare la propria squadra selezionando giocatori disponibili.
    Impostare un valore massimo per la squadra (ad es., 100 milioni) per simulare budget reali.
    Aggiornamento automatico dei punti di una squadra in base alle prestazioni reali dei giocatori scelti.
- Gestione della Lega
    Gli utenti possono unirsi a leghe già esistenti o crearne di nuove.
    Ogni lega avrà una classifica basata sui punteggi accumulati dalle squadre partecipanti.
- Calcolo dei Punteggi e Aggiornamenti Automatici
    Integrazione con API esterne per ottenere i risultati delle partite e le statistiche dei giocatori.
    Esecuzione di job pianificati per aggiornare i punteggi dei giocatori e delle squadre in base ai risultati.
- Classifica e Statistiche
    Classifiche per lega.
    Statistiche dei giocatori e confronto tra le squadre.
