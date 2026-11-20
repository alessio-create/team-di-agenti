# Nuovo agente

Build a custom agent WITH the user, by talking. Where files live: stato.md. Ready-made starting points: `catalogo.md`.

## Regole
- Never invent facts about the business: use the profile and the user's words. A missing fact becomes `[DA COMPLETARE]`.
- One question per message, at most 3 questions in total. Each question offers a default the user can accept with «ok».
- Never write files before the user approves the card (step 4). Exception: the request already gives name, job and what it must never do, or says «senza domande» / «crea subito»: then write directly and show the card after.
- The slug is the role in lowercase with hyphens (`menu-recensioni`, `amministrazione`). Catalogue agents keep the catalogue slug.

## 1. Prepara
Read the profile (missing → send to setup as SKILL.md says, and stop) and `catalogo.md`.
If «Agenti attivi» lists a slug marked `sì` that has no agent files yet, that agent comes first: "Nel tuo profilo c'è già <Nome> (<slug>), ma non l'abbiamo ancora creato. Partiamo da lui?"

## 2. Proponi
Only when the user did not describe the agent ("nuovo agente", "proponimi degli agenti", "che agenti mi servono?").
Propose 3 numbered options, 3 lines each (name and role · what it delivers · first job to try):
1. the catalogue card for the sector of the profile's «Attività», adapted to this business (its competitors, channels, goals);
2. and 3. agents built on the profile's «Obiettivi (90 giorni)» or on a job the user mentioned, or another catalogue card that fits.
End with: «Quale creiamo? Scrivi 1, 2 o 3, oppure descrivimene uno tuo.»

## 3. Intervista
For the chosen agent, ask ONLY what is still missing, in this order:
1. «Come lo chiamiamo?» (default: the catalogue name, or a short Italian first name not already in the team)
2. «Cosa deve consegnarti, e ogni quanto?» (default: the card's «Consegna»)
3. «C'è qualcosa che non deve mai fare?» (default: the card's «Regole»)

## 4. Scheda
Show the agent in at most 10 lines:
**<Nome> (<Ruolo>)** · Lavoro · Consegna · Usa il web: sì/no · Regole · Passa il lavoro a · Primo lavoro.
Ask: «Lo creo così? Puoi correggere qualsiasi riga a parole.» Apply corrections and show the card again until the user agrees.

## 5. Scrivi
Same headings as the built-in agents, in Italian, in the agent's own voice:
- `SOUL.md`: `# <Nome> (<Ruolo>)` · `## Chi sono` (2 lines) · `## Il mio carattere` (3 bullets) · `## I miei valori` (3 bullets) · `## Come parlo` (2 lines).
- `AGENTS.md`: `# Istruzioni di <Nome> (<Ruolo>)` · `## Il mio lavoro` · `## Obiettivi che servo` (the profile's goals it serves) · `## Come lavoro` (the output's exact sections and length; with web: every fact with link and date) · `## Passaggi di consegne` (receives from Leo; hands over to the right colleague and always to the Revisore when something goes out; line format `<Nome> → <Nome>: <cosa>`) · `## Regole` (first line: `Valgono le regole comuni (references/regole-comuni.md).`, then the agent's own rules, the user's words kept).
- Pro: save them in `team/agenti/<slug>/`. Gratis: one downloadable document `agente-<slug>.md` with SOUL.md then AGENTS.md (first line `# <Nome> (<Ruolo>)`), and end with the download notice from stato.md.
- Profile: add `- <slug>: sì` under «Agenti attivi» and `- <slug>: <Nome>` under «Nomi del team» (Gratis: the updated profile as a download).

## 6. Prova
Reply: «Ho aggiunto <Nome> al team. Leo lo userà quando serve. Prova subito: «<primo lavoro>». Per cambiarlo scrivi «<Nome>: …» (es. «<Nome>: più breve»); per spegnerlo metti `no` nel profilo.»

## Modificare un agente
"<Nome>: più breve", "aggiungi una regola a <Nome>", "rinomina <Nome> in …":
- Custom agent: edit ONLY the affected section of its files, then show what changed in 3 lines.
- Built-in agent (Leo, Ada, Giulia, Marco, Sara, Vito): its files belong to the skill. Put the change in the profile instead (a rule under «Regole», a name under «Nomi del team») and say so in one line.
