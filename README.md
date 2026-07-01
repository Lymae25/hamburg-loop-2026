# Incident Tracker

En live webapp med dropdowns og filtre, der gemmer alt i MySQL.
Excel bruges kun til eksport / overblik (knappen "Eksportér til Excel").

## Forudsætninger
- Node.js installeret (https://nodejs.org)
- MySQL installeret og kører

## Opsætning (engangs)

### 1. Opret databasen
I terminal (mac med brew-installeret mysql):

    mysql -u root -p < schema.sql

Eller åbn schema.sql i MySQL Workbench og kør hele filen.

### 2. Indsæt dit MySQL-password
Åbn `server.js` og ret linjen:

    password: 'DIT_PASSWORD_HER',

til dit rigtige MySQL root-password (eller en bruger du har lavet).

### 3. Installér og start
I terminal, fra denne mappe:

    npm install
    npm start

Åbn så browseren på:  http://localhost:3000

## Daglig brug
- "+ Ny incident" åbner en formular med dropdowns
- ✎ redigerer, 🗑 sletter
- Søgefelt + status/prio-dropdowns filtrerer live
- "Eksportér til Excel" henter en færdig .xlsx med samme kolonner

## Senere: del med kolleger
Lige nu kører det kun på din maskine (localhost). Når I vil dele live:
- læg MySQL på en server kollegerne kan nå, ELLER
- brug en gratis cloud-MySQL (fx PlanetScale/Railway) og ret host/user/password i server.js
- kør server.js på en delt maskine/server, så peger alle på samme http-adresse

## Kolonner (samme som dit ark)
STATUS · INC NR · PRIO · NAME · SYSTEM · MARKET · START DATE · COMMENT · ACTIONS
