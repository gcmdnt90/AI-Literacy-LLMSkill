# AI Literacy LLMSkill

Pacchetto portabile `SKILL.md` per creare, eseguire, aggiornare e monitorare un corso personalizzato di alfabetizzazione all'intelligenza artificiale.

*English version available in `README_EN.md`.*

La skill è progettata attorno a un nucleo multipiattaforma:

- Ambienti compatibili con skill OpenAI/Codex/ChatGPT: installa la cartella `ai-literacy-course/`.
- Ambienti compatibili con skill Claude/Anthropic: installa la cartella `ai-literacy-course/` nella posizione in cui vengono caricate le skill personalizzate.
- Agenti locali/open che supportano Agent Skills, come shell per agenti in stile OpenClaw o basate su Ollama: punta l'agente a `ai-literacy-course/SKILL.md`.
- Gemini/Gems e chatbot generici: usa i prompt di adattamento in `adapters/`.

## Cosa fa

- Crea e aggiorna un tracker persistente `ai-literacy-program.md`.
- Costruisce un corso adattivo di alfabetizzazione all'IA per la persona che lo segue.
- Usa una diagnosi integrata con quiz occasionali.
- Tiene traccia delle evidenze rispetto ai domini di AI literacy di Stanford, alle dimensioni MAILS, ai segnali attitudinali GAAIS/GAAIS-IT e alle competenze di IA generativa.
- Aggiorna il corso controllando fonti autorevoli su AI literacy e metodologia quando è disponibile la ricerca web.

## Struttura del repository

```text
AI-Literacy-LLMSkill/
  README.md
  README_EN.md
  LICENSE
  .gitignore
  adapters/
    gemini-gem-instructions.md
    generic-chatbot-prompt.md
  ai-literacy-course/
    SKILL.md
    agents/openai.yaml
    references/
      standards-map.md
      course-update-sources.md
    assets/
      ai-literacy-program-template.md
```

## Installazione

### OpenAI / Codex

Copia `ai-literacy-course/` nella tua directory delle skill, per esempio:

```text
~/.codex/skills/ai-literacy-course
```

Poi invoca:

```text
Use $ai-literacy-course to start or continue my personal AI literacy course.
```

### Claude / Anthropic

Installa la cartella `ai-literacy-course/` come skill personalizzata nella posizione supportata dal tuo prodotto Claude. La skill segue il pattern di directory `SKILL.md` con `references/` e `assets/` opzionali.

### Gemini / Gems

Le Gemini Gems usano istruzioni personalizzate invece dello stesso loader nativo `SKILL.md`. Usa `adapters/gemini-gem-instructions.md` come corpo delle istruzioni della Gem e carica o incolla `ai-literacy-course/SKILL.md` più il template del tracker se il prodotto supporta i file.

### Chatbot generici

Usa `adapters/generic-chatbot-prompt.md`. Allega o incolla `ai-literacy-course/SKILL.md` e chiedi al chatbot di seguirlo come procedura operativa.

## Requisito di persistenza

Il corso ha bisogno di uno stato persistente. Il file di stato preferito è:

```text
ai-literacy-program.md
```

Se l'ambiente non può scrivere o conservare file, la skill dovrebbe chiedere all'utente di abilitare file locali, artifact, memoria di progetto o un altro meccanismo di archiviazione persistente prima di fare affidamento sulla continuità.

## Riferimenti principali

- Stanford Teaching Commons, Artificial Intelligence Teaching Guide.
- Stanford Teaching Commons, Understanding AI Literacy.
- MAILS and MAILS short version.
- GAAIS and GAAIS-IT.
- Generative AI Literacy: Twelve Defining Competencies.

La gestione dettagliata delle fonti si trova in `ai-literacy-course/references/`.
