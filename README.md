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
operator's details. Change it there, then rebuild from a checkout of the app repository, with this
repository checked out next to it, and with today's date if the policy changed. Put in the
operator's name, postal address and email address as section 1 of the published privacy policy
gives them; they are not repeated here.

```bash
OPERATOR_NAME='…' \
OPERATOR_ADDRESS_DE='…, Schweiz' \
OPERATOR_ADDRESS_EN='…, Switzerland' \
CONTACT_EMAIL='…' \
EFFECTIVE_DATE=YYYY-MM-DD \
LAUNCH_STATE=before-launch \
SITE_URL=https://vnznznznz.github.io/night-courier/ \
npm run build:pages -- --out ../vnznznznz.github.io
```

`LAUNCH_STATE=before-launch` puts a notice at the top of every page that Night Courier has not
started and that nothing is processed yet. Build with `LAUNCH_STATE=live` (and `DPA_SINCE`, the date
from which the processing agreement with Supabase demonstrably applies) only as the app repository's
`docs/GO-LIVE.md`, "Where the web pages live", says.

Then commit and push here; GitHub publishes within a minute or two. `.nojekyll` makes GitHub serve
the files as they are, with no theme and nothing loaded from elsewhere, as the privacy policy
promises.
