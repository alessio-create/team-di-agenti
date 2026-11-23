# Installa il team di agenti (istruzioni per Claude)

Sei Claude Code, dentro VS Code, sul computer di una persona che partecipa al workshop «Il tuo team di agenti AI». Installi tu tutto quello che serve: la persona non deve copiare comandi nel terminale.

Come lavori:
- Parli in italiano semplice, una riga per passo: cosa stai facendo e perché. Niente gergo.
- Lanci tu i comandi. Quando VS Code chiede il permesso per un comando, di' alla persona di cliccare **Consenti** e spiega in una riga a cosa serve.
- Prima di installare qualcosa controlla se c'è già: non reinstallare quello che funziona.
- Non chiedere mai password e non scriverle tu. Se serve una password di amministratore, lo dici e la persona la inserisce nella finestra del sistema.
- Se un passo non riesce dopo due tentativi, spiega cosa è successo e vai avanti: il team funziona anche senza Paperclip (passi 4-6).
- Alla fine mostri un riepilogo con ✅ o ⚠️ per ogni passo.

## 1. Il sistema

Capisci se sei su **Windows** o su **Mac** e usa i comandi giusti per quel sistema.

## 2. Node.js (serve a Paperclip)

Controlla con `node -v`. Serve la versione **24.11 o più recente** (Paperclip non parte con le versioni precedenti): se è più vecchia, aggiornala come sotto.

Se manca:
- **Windows:** `winget install -e --id OpenJS.NodeJS.LTS --accept-package-agreements --accept-source-agreements`. Poi, per questa sessione, aggiungi `C:\Program Files\nodejs` al PATH del terminale prima di usare `node` e `npx`.
- **Mac:** se c'è Homebrew (`brew -v`), usa `brew install node`. Altrimenti scarica l'installer ufficiale (la versione LTS da https://nodejs.org) in Download e aprilo con `open`: la persona clicca Continua fino alla fine e inserisce la sua password nella finestra del Mac.

Controlla di nuovo con `node -v`.

## 3. Claude nel terminale (serve a Paperclip per far lavorare gli agenti)

Controlla con `claude --version`. Se manca:
- **Windows (PowerShell):** `irm https://claude.ai/install.ps1 | iex`
- **Mac:** `curl -fsSL https://claude.ai/install.sh | bash`

Poi controlla che sia collegato all'account: lancia `claude -p "rispondi solo: ok"`. Se chiede il login, di' alla persona di aprire un terminale di VS Code (menu Terminale → Nuovo terminale), scrivere `claude`, fare il login nel browser e tornare qui.

## 4. La cartella del team

Scarica e decomprimi il kit nella cartella aperta in VS Code:
- link: https://github.com/alessio-create/team-di-agenti/releases/latest/download/team-di-agenti-kit.zip
- Windows: `Invoke-WebRequest` per scaricarlo, `tar -xf` per decomprimerlo. Mac: `curl -L -o` e `unzip`.

Ottieni una cartella `team-di-agenti` con dentro `PROMPT.md`, `LEGGIMI.md`, `collega-paperclip.mjs`, `avvia-paperclip.cmd` e `avvia-paperclip.command`, la cartella `.claude` (il team) e la cartella `team`. Da qui in poi lavori dentro `team-di-agenti`.

## 5. Paperclip: installalo e accendilo

Se http://127.0.0.1:3100/api/health risponde già `"status":"ok"`, Paperclip è acceso: salta al passo 6.

Altrimenti:
1. Preparalo (una volta sola): `npx -y paperclipai onboard --yes`
2. Accendilo **in una finestra sua**, che resta aperta anche quando chiudi questa chat. Non lanciarlo come comando in background di questa sessione: si spegnerebbe con lei. Usa il file di avvio che c'è nella cartella del team, aperto dal sistema:
   - **Windows:** `explorer.exe avvia-paperclip.cmd`
   - **Mac:** `chmod +x avvia-paperclip.command` e poi `open avvia-paperclip.command`

   Di' alla persona: «Si è aperta una finestra: è Paperclip. Lasciala aperta, puoi ridurla a icona. Le prossime volte la riaccendi con un doppio clic su `avvia-paperclip`.»
3. Aspetta finché http://127.0.0.1:3100/api/health risponde `"status":"ok"` (la prima volta può volerci un minuto o due).

## 6. Collega il team a Paperclip

Dalla cartella `team-di-agenti` lancia:

`node collega-paperclip.mjs "Nome dell'azienda"`

Usa il nome dell'azienda della persona se te l'ha detto, altrimenti `"Il mio team di agenti"`. Lo script crea l'azienda in Paperclip con Leo (Capo dello Staff) e il suo team: Ada, Giulia, Marco, Sara e Vito, con l'organigramma. Paperclip controlla ogni agente per qualche secondo: poi sono pronti.

Apri la board nel browser: http://127.0.0.1:3100 (Windows `Start-Process`, Mac `open`).

## 7. Fine

Mostra il riepilogo e poi spiega, in quattro righe:
1. Per lavorare con il team: **apri la cartella `team-di-agenti` in VS Code** (File → Apri cartella), apri una **nuova chat** di Claude e segui `PROMPT.md`, a partire da «Capo, presentati».
2. In Paperclip vedi l'organigramma. Se crei un lavoro e lo assegni a Leo, Leo parte da solo e lo distribuisce al team.
3. Paperclip resta acceso finché resta aperta la sua finestra. Per riaccenderlo: doppio clic su `avvia-paperclip` nella cartella del team.
4. Gli agenti preparano solo bozze: niente esce senza il tuo ok.
