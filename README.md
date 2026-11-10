# vnznznznz.github.io

Web pages for Night Courier, served by GitHub Pages:

- [`night-courier/`](https://vnznznznz.github.io/night-courier/) – help and contact (also the App
  Store Support URL and Google Play's account deletion page)
- [`night-courier/privacy-policy.de.html`](https://vnznznznz.github.io/night-courier/privacy-policy.de.html)
  – privacy policy (German, binding)
- [`night-courier/privacy-policy.en.html`](https://vnznznznz.github.io/night-courier/privacy-policy.en.html)
  – privacy policy (English translation)

## Changing them

Never edit the HTML here. The text lives in `docs/store/` of the Night Courier app repository
(`privacy-policy.de.md`, `privacy-policy.en.md`, `support-page.md`), with placeholders for the
details below. Change it there, then rebuild from a checkout of the app repository, with this
repository checked out next to it, and with today's date if the policy changed:

```bash
OPERATOR_NAME='Adam Vincus' \
OPERATOR_ADDRESS_DE='Burstwiesenstrasse 80, 8055 Zürich, Schweiz' \
OPERATOR_ADDRESS_EN='Burstwiesenstrasse 80, 8055 Zürich, Switzerland' \
CONTACT_EMAIL='vinnivinz@live.de' \
EFFECTIVE_DATE=2026-11-10 \
SITE_URL=https://vnznznznz.github.io/night-courier/ \
npm run build:pages -- --out ../vnznznznz.github.io
```

Then commit and push here; GitHub publishes within a minute or two. `.nojekyll` makes GitHub serve
the files as they are, with no theme and nothing loaded from elsewhere, as the privacy policy
promises.
