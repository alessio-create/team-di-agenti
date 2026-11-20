# Dove vivono i file

## Modalità di esecuzione
- **Pro**: the Agent tool is available → dispatch agents to subagents (see capo.md).
- **Gratis**: no Agent tool → play the agents yourself, in sequence.

## Dove leggere e scrivere
- If you can read and write files in a working folder (Claude Code, Cowork): use
  - profile: `team/profilo.md`
  - custom agents: `team/agenti/<slug>/` (`SOUL.md` + `AGENTS.md`)
  - outputs: `team/lavori/AAAA-MM-GG-<slug>-<titolo>.md`
  - diary of each agent: `team/memoria/<slug>.md`
  - noticeboard (handovers, open items, Proposte): `team/bacheca.md`

  Create the folders and files if they are missing.
- Otherwise (claude.ai):
  - The profile is the document "Profilo aziendale" in the Project's knowledge or in this conversation.
  - Each agent's diary is the document `memoria-<slug>.md`; the noticeboard is the document `bacheca.md`. Both are Project documents.
  - Custom agents are Project documents whose first line is `# <Nome> (<Ruolo>)`.
  - Every new or changed file (profile, agent, output, diary, noticeboard) is created as a downloadable file: an updated version of an existing document is given as a new download. End with:
    "Scarica il file e aggiungilo alla conoscenza del Progetto: così il team se lo ricorda."

## Gli agenti del team
The six built-in agents live in the skill, in `agenti/<slug>/` (`agent.yaml`, `SOUL.md`, `AGENTS.md`, `TOOLS.md`, `HEARTBEAT.md`, `MEMORY.md`). The folder name is the slug used everywhere: in the profile («Agenti attivi»), in `agent.yaml`, in file names and in the diary. The first line of each `SOUL.md` is `# <Nome> (<Ruolo>)`: that is how a dispatched agent is recognised.
 The name in that title is the default name; the profile's «Nomi del team» overrides it.
