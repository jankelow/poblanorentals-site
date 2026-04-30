# poblanorentals.com

Static one-pager + privacy/terms for the public-facing Poblano Rentals brand.

Built primarily to satisfy Twilio A2P 10DLC brand verification (carriers want a real website with privacy/terms before they'll let you send SMS), but also a perfectly fine landing page on its own.

## Files

- `index.html` — landing
- `privacy.html` — privacy policy with SMS-specific clauses
- `terms.html` — terms of service with SMS opt-in language
- `vercel.json` — basic security headers + clean URLs
- `logo.png` — copy `Poblano Rentals Logo.png` here as `logo.png`. The pages reference it via `/logo.png` for the favicon. (Optional — pages still render with a typographic placeholder if missing.)

## Deploy to Vercel

This is intentionally a separate Vercel project from `poblano-tracker`. They share a brand but nothing else.

```
cd poblanorentals-site
git init
git add .
git commit -m "Initial Poblano Rentals marketing site"
gh repo create poblanorentals-site --public --source=. --push
vercel --prod
```

When prompted, link to a new project (not the existing `poblano-pms`).

## Connect the domain

1. Buy `poblanorentals.com` at Cloudflare Registrar (~$10/yr) or Namecheap.
2. Vercel project → Settings → Domains → Add `poblanorentals.com` and `www.poblanorentals.com`.
3. Vercel will show the DNS records to set. Update them at your registrar.
4. SSL provisions automatically within ~2 minutes.

## After deploy — A2P registration

Use these URLs in the Twilio brand registration:

- **Company website**: `https://poblanorentals.com`
- **Privacy policy URL**: `https://poblanorentals.com/privacy`
- **Terms URL**: `https://poblanorentals.com/terms`
- **Opt-in disclosure URL**: `https://poblanorentals.com/#text-message-communication`

## Edits

Pure HTML, no build step. Edit a file, push to git, Vercel redeploys in ~10 seconds.

If you want to add real photography of the buildings, drop them in this folder and reference via `<img src="/wellington.jpg">` etc. Keep them under 500KB each (compress at squoosh.app).
