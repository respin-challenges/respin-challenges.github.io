# respin-challenges.github.io

Landing page for the challenges run under the [RESPIN project](https://respin.iisc.ac.in/), SPIRE Lab, IISc Bengaluru.

Live at https://respin-challenges.github.io/

This repository holds only the front page. It lists every challenge and links to that challenge's own website. Challenge content (tasks, data, dates, leaderboards) belongs in the challenge's own repository or site, not here.

## Contents

```
index.html               Landing page: about RESPIN, challenge cards, resources, contact
404.html                 "Page not found" (styles inline; see the note in the file)
.nojekyll                Tells GitHub Pages to serve the files as they are
assets/css/site.css      Styles, trimmed from the MADST 2027 site so both look alike
assets/img/favicon.svg   Site icon
```

Plain HTML and CSS. There is no build step and no JavaScript.

## Adding a new challenge

1. **Create the challenge's repository** in the [respin-challenges](https://github.com/respin-challenges) organisation, named `<challenge><year>` in lower case, for example `madst2027`.
2. **Turn on GitHub Pages** in that repository: *Settings → Pages → Build and deployment → Deploy from a branch*, branch `main`, folder `/ (root)`. The site is then served at `https://respin-challenges.github.io/<challenge><year>/`. Wait until that address loads.
3. **Add a card to `index.html`.** In the section marked `CHALLENGES`, copy one block from a `<!-- CHALLENGE CARD: ... -->` comment to its matching `<!-- /CHALLENGE CARD: ... -->` comment. Paste it at the top of the list, since cards go newest first. Then edit:
   - the link: `/<challenge><year>/` for a site in this organisation, or the full URL for a site hosted elsewhere;
   - the name, venue and year, full title and one-line description;
   - the status word, and the `is-current` class (see below).

### Changing a challenge's status

Each card has one status word:

```html
<span class="status"><span class="visually-hidden">Status: </span>Upcoming</span>
```

Change `Upcoming` to `Ongoing` or `Completed`. Nothing else needs to change.

While a challenge is upcoming or ongoing, its card has `class="challenge is-current"`, which fills the status label and darkens the card's left edge. When it is completed, change this to `class="challenge"`.

### MADST 2027 (prepared, not shown yet)

The MADST 2027 card is already in `index.html`, inside an HTML comment, so it does not appear on the page. It stays hidden until ASLI 2027 accepts the MADST challenge proposal (notification expected 17 Dec 2026). To show it:

1. Check that https://respin-challenges.github.io/madst2027/ loads.
2. In `index.html`, inside the `CHALLENGE CARD: MADST 2027` block, delete the line that starts with `<!-- HIDDEN` and the line `END HIDDEN -->`. The card is already marked `Upcoming` with the `is-current` class.
3. In `404.html`, do the same for the MADST 2027 link.

HTML comments cannot be nested. To hide another card the same way, put the `<!-- HIDDEN` and `END HIDDEN -->` lines inside its `CHALLENGE CARD` markers, not around them.

### Once a year

The footer year in `index.html` is typed in by hand. Update it each January.

## Previewing locally

```sh
cd respin-challenges.github.io
python3 -m http.server 8000
```

Then open http://localhost:8000/.

- Links to challenge sites in other repositories of this organisation, such as `/madst2027/` ([respin-challenges/madst2027](https://github.com/respin-challenges/madst2027)), will not load locally.
- Python's server does not use `404.html` for missing pages. To see it, open http://localhost:8000/404.html.

## Deploying

*Settings → Pages → Build and deployment → Deploy from a branch*, branch `main`, folder `/ (root)`. Each push to `main` starts a *pages build and deployment* run under the *Actions* tab. The site updates a minute or two after that run turns green.
