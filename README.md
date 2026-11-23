# respin-challenges.github.io
Websites for challenges under the RESPIN project, SPIRE Lab, IISc Bengaluru.

Live at https://respin-challenges.github.io/

## Contents

```
index.html   Landing page: one entry per challenge (plain HTML, styles inline, no JavaScript)
.nojekyll    Tells GitHub Pages to serve the files as they are
```

## Challenges

| Challenge | Venue | Website |
|---|---|---|
| MADASR 2.0 | ASRU 2025 | https://sites.google.com/view/respinasrchallenge2025/home |
| MADASR | ASRU 2023 | https://sites.google.com/view/respinasrchallenge2023/home |

MADST (ASLI 2027) lives in its own repository, [respin-challenges/madst2027](https://github.com/respin-challenges/madst2027), and is served at https://respin-challenges.github.io/madst2027/ once GitHub Pages is enabled there. Its entry is already in `index.html` inside an HTML comment; uncomment it after the ASLI 2027 challenge-proposal notification (17 Dec 2026) and after that URL loads.

## Adding a challenge

Copy one `<li class="challenge">` block in `index.html`, newest first, and change the venue, short name, full title and link. A challenge hosted in this organisation as a repository named `<repo>` is linked as `<repo>/` (relative), which resolves to `https://respin-challenges.github.io/<repo>/`.

## Deploying

Settings > Pages > Deploy from a branch > `main`, `/ (root)`. Changes go live a minute or two after each push to `main`.
