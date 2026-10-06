# DNA Gym AI website

Small public website for [dnagymai.com](https://dnagymai.com). It exists so DNA Gym AI can publish a Privacy Policy, Terms of Use, Health & Fitness Disclaimer and support contact for App Store and Google Play submission.

This is a separate project from the DNA Gym AI mobile app. Do not copy these files into the mobile app repository.

## Architecture

Static HTML and one CSS file. There is no JavaScript, no framework, no build step, no analytics, no cookies banner and no support form.

Clean URLs are directories inside `public/`:

| URL | File |
| --- | --- |
| `/` | `public/index.html` |
| `/privacy` | `public/privacy/index.html` |
| `/terms` | `public/terms/index.html` |
| `/health-disclaimer` | `public/health-disclaimer/index.html` |
| `/support` | `public/support/index.html` |

Cloudflare Pages serves `privacy/index.html` for `/privacy` and `/privacy/`. No `.html` suffix is required. This README stays outside `public/`, so it is not part of the deployed site.

## Preview locally

From this folder:

```bash
python3 -m http.server 8080 --directory public
```

Open the local address the server prints. That address is only for preview.

## Cloudflare Pages

Do not change DNS from this repository. Connect the site in the Cloudflare dashboard when you are ready.

- Framework preset: None
- Build command: leave empty
- Build output directory: `public`
- Root directory: repository root
- Environment variables: none

After the first Pages deploy, add the custom domain `dnagymai.com` in the Pages project. The domain is already on Cloudflare.

Production canonical URL: `https://dnagymai.com`

## Store buttons later

The app does not have final Apple App Store or Google Play URLs. The homepage shows “App store availability coming soon.” and does not link to a store.

When real URLs exist, add them inside `#store-downloads` in `public/index.html`, using the `store-link` class already in `public/css/styles.css`. Remove the coming-soon line at that time. Do not add a link until the URL is the live store listing.

## Legal sources

Public pages are formatted from the mobile app drafts on branch `cursor/release-readiness-audit-3339` at commit `08aea962d2f336ca6b2e0c0869cdc7e4a05b9cbe`:

- `docs/legal/PRIVACY_POLICY.md`
- `docs/legal/TERMS_OF_USE.md`
- `docs/legal/HEALTH_AND_FITNESS_DISCLAIMER.md`

Also read, and not published as pages: `docs/legal/README.md`, `docs/legal/STORE_PREP.md`.

These are product drafts. They are not represented as lawyer-reviewed.

### Wording changed only where the draft told the operator to publish a contact

Privacy Policy contact in the source said a customer support address was not configured in the app yet, and that the operator should publish one before store submission. This site publishes `support@dnagymai.com` and keeps the warning not to send personal information to `noreply@dnagymai.com`.

Terms contact in the source said support details would be published with the public terms. This site publishes `support@dnagymai.com` and keeps the sentence that this is not the noreply sender used for invitation and Auth email.

Two source sentences that said the public web page was not live yet are not repeated on the live page. The draft status, version date and “not legally reviewed” wording remain.

The in-app legal copy was not edited. It may still say a support address is not configured.

### Owner decisions still open

- Governing law is not set.
- Paid prices and refund rules are not set. This version does not sell subscriptions.
- The liability paragraph says it is not a jurisdiction-specific limitation clause and should be reviewed before publication.
- Store questionnaires still need the owner to confirm minimum age. That decision is in `STORE_PREP.md` and is not on this website.
- Reviewer account placeholders in `STORE_PREP.md` were not copied here.

Support email used on this site: `support@dnagymai.com`.

## Brand

Logo and favicon are the existing DNA Gym AI assets from the mobile app. Colours follow the app: black background, white text, cyan `#00D4FF`.
