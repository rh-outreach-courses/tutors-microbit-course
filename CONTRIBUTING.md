# Contributing

This repository is a [Tutors](https://github.com/tutors-sdk/tutors) course for the Micro:bit workshop.

## Course layout

```text
course.md                 # Course title + summary
properties.yaml           # Course properties
topic-NN-name/
  topic.md                # Topic title + summary
  topic.png               # Topic card image
  unit-1/
    main-lesson.md        # Unit title
    book-a/               # Lab (folder of numbered steps)
      00.Something.md
      01.01.md
      ...
      img/                # Optional images referenced from steps
```

Tutors discovers topics by folder name (`topic-*`). Keep numeric prefixes so topics sort in workshop order.

## Adding or editing a topic

1. Copy an existing topic folder as a template, or create `topic-NN-short-name/` with `topic.md`, `topic.png`, and at least one `unit-*`.
2. Labs live in `book-*` folders. The first heading in each step markdown becomes the step title in Tutors.
3. Match the tone of neighbouring labs (short, practical, screenshot-friendly).
4. Facilitator-only material should be clearly titled (e.g. `Advanced / Facilitator: ...`).

## Local build

Requires [Deno](https://deno.land/).

### Preview (HTML)

```bash
deno run -A jsr:@tutors/tutors-publish-html
```

Opens as `html/index.html` (or serve `html/` with a local static server). **Do not commit `html/`** — it is gitignored and for local preview only.

### Publish build (JSON)

```bash
deno run -A jsr:@tutors/tutors
```

This writes the generated site into `json/`.

### Publish artifacts (`json/`)

Regenerating and committing `json/` is a **separate publish step**, held for later. You do **not** need to rebuild or commit `json/` for every content change while that workflow is deferred. Netlify can still run the build command on deploy (see README).

## Netlify

See [README.md](./README.md) for Netlify import settings (build command and publish directory). Prefer linking here rather than duplicating those steps.
