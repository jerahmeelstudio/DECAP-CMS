# Jerahmeel Studio — Portfolio Website

A premium, one-page portfolio site with a no-code admin dashboard (Decap CMS) so you can edit everything — text, images, portfolio, testimonials, contact links — without touching any code.

## What's inside

- `src/index.njk` — the page content/structure
- `src/_data/site.json` — **all editable content lives here** (this is the file the admin dashboard edits)
- `src/css/style.css` — all styling
- `src/js/main.js` — small vanilla JS (scroll reveal, back-to-top, WhatsApp fab)
- `src/admin/` — the Decap CMS dashboard (`/admin` on your live site)
- `.eleventy.js` — builds the site from the templates + data into a `_site` folder Netlify publishes

It's built with [Eleventy](https://www.11ty.dev/), a very lightweight static site builder — no heavy frameworks, fast output, good for PageSpeed.

## One-time setup (about 15 minutes)

### 1. Put this project on GitHub
1. Create a new, empty repository on GitHub (e.g. `jerahmeel-studio`).
2. Upload everything in this folder to that repository (drag-and-drop upload works fine on GitHub's website, or ask a developer friend to `git push` it once).

### 2. Connect the repo to Netlify
1. Go to [app.netlify.com](https://app.netlify.com) → **Add new site → Import an existing project**.
2. Pick GitHub, then select your `jerahmeel-studio` repo.
3. Build settings should auto-fill from `netlify.toml` (build command `npm run build`, publish folder `_site`). Click **Deploy**.
4. Once deployed, you'll get a URL like `https://your-site-name.netlify.app`.

### 3. Turn on the admin dashboard (Netlify Identity + Git Gateway)
This is what lets you log in and edit content without code.
1. In your Netlify site dashboard: **Site configuration → Identity → Enable Identity**.
2. Under **Registration**, set it to **Invite only** (so strangers can't sign up).
3. Scroll to **Services → Git Gateway → Enable Git Gateway**.
4. Go to the **Identity** tab → **Invite users** → invite yourself with your email.
5. Check your email and accept the invite — it'll ask you to set a password on your site's `/admin` page.

### 4. Update your site URL
In `src/_data/site.json`, change `"siteUrl"` under `"seo"` to your real Netlify (or custom) domain, so SEO tags and shareable links are correct. You can do this later from inside the dashboard too, under **SEO**.

## Editing your site day-to-day

Go to `https://yoursite.netlify.app/admin`, log in, and you'll see plain-English fields for:

- Hero headline, subtext, and button labels
- All 4 service cards
- Portfolio: your YouTube video ID, and the 2 photo-editing + 2 AI-visual images
- Why Choose Us cards
- Testimonials (name, role, photo, quote)
- About section text
- Phone, email, WhatsApp number, Facebook, Instagram, YouTube links
- Footer text

Click **Publish** after any change — Netlify will automatically rebuild and update your live site in about a minute.

## Before you go live, replace these placeholders

- **Phone / WhatsApp number** — currently a placeholder (`+234 000 000 0000`). Update in the dashboard's Contact section. The WhatsApp number should be digits only with country code, no `+` or spaces (e.g. `2348012345678`).
- **Portfolio images** — the 4 portfolio images and 3 testimonial photos are elegant placeholder graphics, not real photos. Upload your real work through the dashboard's image fields.
- **YouTube video** — currently points to a placeholder video ID. Replace with your real ad video's ID (the part after `v=` in its YouTube URL).
- **Social links** — Facebook, Instagram, and YouTube URLs are placeholders — update them in Contact & Social Links.
- **Social share image** — `og-cover.svg` is a generated placeholder for link previews (WhatsApp/Facebook shares); swap it for a real branded image if you have one.

## Performance & SEO notes

- Images use `loading="lazy"`, the YouTube embed uses the privacy-friendly `youtube-nocookie.com` domain and lazy-loads.
- Fonts are loaded from Google Fonts with `preconnect` for speed.
- All animations are CSS-only (the aurora background, hover states) and respect `prefers-reduced-motion`.
- Meta title, description, Open Graph, Twitter card tags, and structured data (`schema.org` ProfessionalService) are all wired to the CMS fields, so editing SEO text in the dashboard updates them automatically.
- No CSS/JS frameworks — just vanilla CSS and a ~50-line JS file, kept small for fast loading and good PageSpeed scores.
