# AI Literacy LLMSkill

Portable `SKILL.md` package for creating, running, updating, and tracking a personalized AI literacy course.

The skill is designed around a cross-platform core:

- OpenAI/Codex/ChatGPT skill-compatible environments: install the `ai-literacy-course/` folder.
- Claude/Anthropic skill-compatible environments: install the `ai-literacy-course/` folder where custom skills are loaded.
- Local/open agents that support Agent Skills, such as OpenClaw-style or Ollama-backed agent shells: point the agent at `ai-literacy-course/SKILL.md`.
- Gemini/Gems and generic chatbots: use the adapter prompts in `adapters/`.

## What It Does

- Creates and updates a durable `ai-literacy-program.md` tracker.
- Builds an adaptive AI literacy course for the learner.
- Uses embedded diagnosis with occasional quizzes.
- Tracks evidence across Stanford AI literacy domains, MAILS dimensions, GAAIS/GAAIS-IT attitude signals, and generative-AI competencies.
- Updates the course by checking authoritative AI literacy and methodology sources when web/search is available.

## Repo Structure

```text
AI-Literacy-LLMSkill/
  README.md
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

## Install

### OpenAI / Codex

Copy `ai-literacy-course/` into your skills directory, for example:

```text
~/.codex/skills/ai-literacy-course
```

Then invoke:

```text
Use $ai-literacy-course to start or continue my personal AI literacy course.
```

### Claude / Anthropic

Install the `ai-literacy-course/` folder as a custom skill in the skill location supported by your Claude product. The skill follows the `SKILL.md` directory pattern with optional `references/` and `assets/`.

### Gemini / Gems

Gemini Gems use custom instructions rather than the same native `SKILL.md` loader. Use `adapters/gemini-gem-instructions.md` as the Gem instruction body, and upload or paste `ai-literacy-course/SKILL.md` plus the tracker template if the product supports files.

### Generic Chatbots

Use `adapters/generic-chatbot-prompt.md`. Attach or paste `ai-literacy-course/SKILL.md` and ask the chatbot to follow it as an operating procedure.

## Persistence Requirement

The course needs durable state. The preferred state file is:

```text
ai-literacy-program.md
```

If the environment cannot write or preserve files, the skill should ask the user to enable local files, artifacts, project memory, or another durable storage mechanism before relying on continuity.

## Main References

- Stanford Teaching Commons, Artificial Intelligence Teaching Guide.
- Stanford Teaching Commons, Understanding AI Literacy.
- MAILS and MAILS short version.
- GAAIS and GAAIS-IT.
- Generative AI Literacy: Twelve Defining Competencies.

Detailed source handling is in `ai-literacy-course/references/`.
