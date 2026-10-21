# scaffold-sample

A minimal sample scaffold for `genai-logic create --from_git`.  Alter to fit your organizations standards.

## What this is

GenAI-Logic project creation always starts from the built-in `prototypes/base`
template. `--from_git` lets you **overlay** your own files on top of that base
— the same mechanism used internally for sample projects (Northwind, Chinook,
etc.). Your files replace or add to base's; anything you don't provide (API
generation, Admin App, database models, security, etc.) still comes from base
as usual.

This repo is that overlay, kept intentionally small so you can see the
mechanism clearly:

- `readme.md` — this file, replaces base's root readme after creation
- `logic/declare_logic.py` — a placeholder rule file, proving logic-overlay
  works

## Try it

```bash
genai-logic create --project-name=my_project \
  --db_url=sqlite:///samples/dbs/starter.sqlite \
  --from_git=https://github.com/ApiLogicServer/scaffold-sample
```

## Extending

Clone this repo and add your own organization's conventions — a house style
`readme.md`, starter `logic/declare_logic.py` rules, `security/` roles, CI
config, whatever your team wants every new project to start with. Any file
path that exists in your fork overlays the matching file in `prototypes/base`;
anything you omit is left as `base` provides it.
