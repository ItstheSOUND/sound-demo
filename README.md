# SOUND — hosted + gated demo (staged, not live yet)

A one-field **email gate** in front of the interactive prototype. Fill email → land on the demo. Emails are captured so every try becomes a lead.

- `index.html` — the gate (branded, email form)
- `prototype.html` — the demo with a "PROTOTYPE — illustrative" banner baked in

**Nothing is live until you do the deploy step below.** Flip it on when you want it.

## Flip it on (Netlify — recommended, ~5 min, free, captures emails)
1. Go to **netlify.com** → sign in with GitHub → **Add new site → Import from Git** → pick `ItstheSOUND/sound-demo`.
2. Deploy (no build command; publish directory = `/`). You get a live URL like `sound-demo.netlify.app`.
3. Netlify auto-detects the form. Emails land in **Site → Forms → demo-access** (export CSV, or set an email notification / Zapier to your list).
4. **Custom domain (optional):** Site → Domain settings → add `demo.itsthesound.com`, then add the CNAME Netlify shows you at your DNS.
5. **Squarespace button:** add a Button block linking to your Netlify (or `demo.itsthesound.com`) URL — label it "Try the prototype →".

That's the whole switch. To take it down later, unpublish the Netlify site.

## Alternative (GitHub Pages)
Pages will *host* it, but it has **no form handling** — the email won't be captured. If you prefer Pages, point the form at a free **Formspree** endpoint instead: in `index.html`, change the `<form action="/prototype.html">` to `action="https://formspree.io/f/YOUR_ID"` and add `<input type="hidden" name="_next" value="https://YOUR-PAGES-URL/prototype.html">`.

## Notes
- The demo is client-side only — fake data, gated payments, synthetic audio. Safe to expose.
- `robots: noindex` is set on the gate so it won't show up in search until you want it to.
- To refresh the demo after a rebuild: regenerate `SOUND_Demo.html`, re-run the banner-injection step, and replace `prototype.html`.
