# ututx.github.io

Source of my personal homepage, published with GitHub Pages.

Site: <https://ututx.github.io/>

Plain static site: hand-written HTML + CSS, no framework, no build step — clone it and start editing.

## What's on the page

`index.html` has four blocks:

- **hero** — avatar, one-line tagline, links to GitHub and macOS-DroidVM
- **about** — my attempts at macOS on DroidVM: the UEFI boot chain (UniXNU / DarwinBoot), device trees (ADT / FDT), crosvm and Gunyah virtualization, and packaging the whole thing as an importable `.vmpkg`
- **projects** — three cards: macOS-DroidVM, the vmpkg tool, and this repo
- **notes** — points to the write-ups kept in the macOS-DroidVM repository

## Layout

```
.
├── index.html                  # the whole page lives here
├── styles.css                  # all styles
├── images/
│   └── create-octocat.png      # avatar
├── README.md                   # 中文说明
└── README.en.md                # this file
```

There is no `package.json` and no build output — GitHub Pages serves the sources as they are.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

For style-only tweaks you can also just open `index.html` directly; every reference is a relative path.

## Where to change things

- **Colors** — the `:root` variables at the top of `styles.css` (`--bg`, `--accent`, …) drive the whole theme
- **Copy** — the matching `<section>` in `index.html`
- **Narrow screens** — the `@media (max-width: 480px)` block at the end of `styles.css`
- **Footer year** — the value inside `<span id="year">` in `index.html` is hard-coded

## Deployment

GitHub Pages publishes straight from the root of the `master` branch; every push to `master` triggers a rebuild, usually live within a minute.

No GitHub Actions needed — it's all static files. Note that GitHub Pages requires a public repository on free accounts.

## Related repositories

- [macOS-DroidVM](https://github.com/ututx/macOS-DroidVM) — image building and boot-chain debugging for running macOS inside DroidVM
- [UniXNU-droidvm](https://github.com/Droid-VM/UniXNU-droidvm) — UniXNU device repository for DroidVM guests
