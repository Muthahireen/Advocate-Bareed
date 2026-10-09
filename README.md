# Advocate Bareed - Campaign Website

Static website (plain HTML, CSS and JavaScript). No build step needed.

## Folder structure
```
index.html          page content
css/style.css       all styling
js/app.js           pillars, countdown, WhatsApp form, share, QR on page
js/vendor/          QR library (bundled, works offline)
assets/photo.png    candidate photo
scripts/make-qr.js  creates the print-ready QR code
netlify.toml, vercel.json   deploy settings
```

## Run in VS Code
1. File > Open Folder... and choose this folder.
2. Install the **Live Server** extension (VS Code will suggest it).
3. Right-click `index.html` > **Open with Live Server**. The site opens at http://127.0.0.1:5500

No VS Code? Run `npm run dev` in the terminal (needs Node.js).

## Deploy (free)
**Easiest - Netlify Drop:** open https://app.netlify.com/drop and drag this whole folder in. You get a live link in seconds.

**GitHub Pages:** push the folder to a GitHub repo > Settings > Pages > Deploy from branch > main / root.

**Vercel:** `npx vercel` inside this folder, or import the GitHub repo at vercel.com.

## Make the QR code
After deploying, run (needs Node.js):
```
npm install
npm run qr -- https://your-live-site.netlify.app
```
This creates `qr/qr.png` (for printing) and `qr/qr.svg` (scales to any size). Use the final live address, since a QR always points to exactly what you give it.

## Edit content
- Vision, mission pillars, WhatsApp number: `js/app.js` and `index.html`
- Colours: the `:root` block at the top of `css/style.css`
- Election date and countdown: `target` date in `js/app.js`
- Replace the photo by overwriting `assets/photo.png` (keep the same name)
