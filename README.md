# Morton Lookbook

A GitHub Pages site for Morton Industries to review the Engagement Campaign assets, built the same way as `osf-lookbook` and `hike-lookbook`. Each asset gets its own page with a no-login comment box so Morton can leave feedback directly.

## What's in here

```
morton-lookbook/
├── index.html              (hub — links to every asset)
├── newsletter.html
├── website-listing.html
├── benefit-portal.html
├── flyer.html
├── table-tent.html
├── internal-posts.html
├── emails.html
├── mailer.html
├── sms.html
├── css/style.css
├── js/comments.js          (comment widget — don't need to edit)
├── js/comments-config.js   (Apps Script URL goes here)
├── js/nav.js               (prev/next arrows — shared across all pages)
└── apps-script/Code.gs     (deployed as a standalone Apps Script project)
```

PowerPoint is intentionally left off this lookbook for Morton.

## Assets

- `MORTON NEWSLETTER.pdf`, `MORTON FLYER.pdf`, `MORTON TABLE TENT.pdf`, `MORTON MAILER.pdf` — embedded directly as PDFs.
- `MORTON EMAILS 1.png`, `MORTON EMAILS 2.png` — the two-email sequence, each shown side by side with click-to-zoom.
- SMS, Website Listing, Benefit Portal, and Internal Posts are coded HTML/CSS recreations matching the current Morton Claude Design files — no separate asset files needed.

## Commenting (Google Sheet + Apps Script)

Comments are backed by a "Morton Lookbook Comments" Google Sheet and a standalone Apps Script project deployed as a web app (Execute as: Me, Who has access: Anyone), pointed at that Sheet by ID. The deployed `/exec` URL lives in `js/comments-config.js`.

If the script ever needs to be redeployed, update the same deployment (Deploy → Manage deployments → Edit → New version) so the URL doesn't change.

## GitHub Pages

Settings → Pages → Source: Deploy from branch → Branch: main / (root). Live at:

```
https://tinnguyen-hm.github.io/morton-lookbook/
```

## Notes

- The comment widget posts as `text/plain` (not `application/json`) on purpose — this avoids a CORS preflight request that Apps Script Web Apps don't handle well.
- No comment moderation is built in. If you want to hide/delete a comment, just delete its row in the Sheet.
