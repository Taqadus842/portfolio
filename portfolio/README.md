# Ume Taqadus — Portfolio

## Deploying to Netlify

**Option A — drag and drop (fastest):**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag this whole folder onto the page
3. Done — you'll get a live URL immediately. You can rename it under Site settings > Domain management.

**Option B — connect to GitHub (recommended long-term):**
1. Push this folder to a GitHub repo
2. On [netlify.com](https://netlify.com), click "Add new site" > "Import an existing project"
3. Connect your GitHub repo
4. Leave the build command blank and set the publish directory to `.` (it's already set in `netlify.toml`)
5. Deploy — any future `git push` will auto-redeploy the site

## Before you deploy — one thing to fix

The contact form currently points to a placeholder Formspree endpoint:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

To make it actually send you emails:
1. Go to [formspree.io](https://formspree.io) and sign up free
2. Create a new form, copy the form endpoint it gives you (looks like `https://formspree.io/f/abc123xy`)
3. Replace `YOUR_FORM_ID` in `index.html` with your real ID

Without this step, the form will look fine but won't actually send anywhere.

## What changed from the old version

- Added **Experience** section (your 4 internships, in a timeline)
- Added **Projects** section with a flagship project (Adaptive LLM Routing System) plus 4 supporting projects, each linked to GitHub
- Replaced the generic "Services" section with a real **Skills** section based on your actual tech stack
- Added **Certifications** section
- Removed the fake testimonials (Sarah Lee / Marilyn / Emily Brown were placeholder text, not real reviews)
- Removed the cartoon avatar image — layout now works cleanly without a photo; you can add a real one later if you want
- Fixed the contact form so it can actually send messages (was previously `action="#"`, which does nothing)
- Fixed a broken CSS `<link>` tag that had a stray line break in it
- Switched CV download to a PDF instead of a `.docx` (more universally viewable)
- Fixed absolute asset paths (`/assets/...`) that could break depending on hosting setup

## Local preview

Just open `index.html` in a browser, or run a local server from this folder:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.
