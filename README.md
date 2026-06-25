# Basbaas — After Dark website

Static marketing site for Basbaas Authentic Somali Cuisine (SE18, London).
Dark-green & gold "After Dark" theme. No build step — pure static files.

## Structure

```
index.html              Root entry — redirects to the home page
afterdark/
  Home.dc.html          Landing page
  Menu.dc.html          Full menu
  About.dc.html         Our story
  Events.dc.html        Private events + enquiry form
  Gallery.dc.html       Photo gallery
  Contact.dc.html       Contact, booking form, map
  Header.dc.html        Shared nav (loaded by each page)
  Footer.dc.html        Shared footer (loaded by each page)
  support.js            Client runtime that renders the pages
assets/
  brand/                Logos & favicons
  img/                  Dish photography
vercel.json             Routing + caching config
```

## Local preview

Serve the folder over HTTP (pages fetch shared header/footer, so `file://` won't work):

```bash
npx serve .
# then open http://localhost:3000
```

## Deploy to Vercel

1. Push this folder to a GitHub repo (see below).
2. In Vercel: **Add New → Project → Import** the repo.
3. Framework preset: **Other**. Build command: *(none)*. Output dir: `.` (root).
4. Deploy. Clean routes like `/menu`, `/about`, `/contact` are wired in `vercel.json`.

Or deploy straight from the CLI:

```bash
npm i -g vercel
vercel        # preview
vercel --prod # production
```

## Push to GitHub

```bash
git init
git add .
git commit -m "Basbaas After Dark website"
git branch -M main
git remote add origin https://github.com/<you>/basbaas-afterdark.git
git push -u origin main
```
