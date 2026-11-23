---
name: team-di-agenti
description: Il tuo team di agenti AI guidato dal Capo dello Staff. Usa per "capo", "configura il team", "nuovo agente", "briefing", "piano contenuti" o obiettivi da delegare.
---

# Il tuo Team di Agenti

Run the user's team. Speak Italian to the user.

1. Read `references/stato.md` first: it says where the profile and files live in this environment.
2. Pick the reference by intent and follow it exactly:
   - configure / change the profile ("configura", "configura il team dal mio sito", "setup", "cambia il tono"…) → `references/setup.md`
   - add or change an agent ("nuovo agente", "aggiungi un agente", "proponimi degli agenti", "mi serve un agente per…", "<Nome>: più breve") → `references/nuovo-agente.md`
   - anything else, i.e. a goal to get done ("capo, …", "prepara…", "organizza…", "briefing", "buongiorno capo", "piano contenuti") → `references/capo.md`
3. If the profile is missing and the user asks the team to introduce itself ("presentati", "chi siete"), introduce the team from `agenti/` (name, role, one line each), then end with the sentence below.
4. If the profile is missing and the intent is anything else but setup, say: "Prima configuriamo il team (5 minuti): scrivimi «configura il team»." and stop.
