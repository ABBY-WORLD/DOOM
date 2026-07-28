# SCROLL

Mobile-first art scrolling app with two feeds:

- Then: public-domain/open-access artworks from museum APIs.
- Now: curated image-heavy Are.na channels with local caching and shuffled reloads.

It also includes saved boards, source links, and SomaFM ambient radio controls.

Live site: https://abby-world.github.io/SCROLL/

Run locally with any static server, for example:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Desktop

On screens 960px and wider the app switches to a full-viewport desktop layout:
the artwork fills the screen, metadata sits bottom-left, actions bottom-right,
and keyboard shortcuts are shown at the bottom (arrow keys to scroll and switch
feeds, `R` for a random radio station). Between 620px and 959px the classic
phone-frame presentation is kept.

## Rolling back to the live version

The deployed site always tracks `main`. Improvements land on separate branches
and only reach the live site when merged, so:

- To preview changes without touching the live site: keep them on their branch.
- To roll back after a merge: `git revert -m 1 <merge-commit>` on `main`, or
  reset `main` to the last known-good commit and force-push.
- The last version before the stability/desktop overhaul is the commit tagged
  by `git log --oneline` as `61be4aa` ("Add files via upload").
