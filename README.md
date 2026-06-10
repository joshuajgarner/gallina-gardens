# Gallina Gardens Website

**Live site:** [gallinagardens.co.uk](https://gallinagardens.co.uk)

---

## Folder structure

```
gallina-gardens/
├── index.html                    ← The website (HTML, CSS and JS)
├── send.php                      ← PHP mail handler (for FastHosts only)
├── CNAME                         ← Domain name for GitHub Pages
├── README.md                     ← This file
├── .gitignore                    ← Files Git should ignore
│
├── assets/
│   ├── favicons/                 ← Browser tab icons (do not edit)
│   │   ├── favicon.ico
│   │   ├── favicon-32x32.png
│   │   ├── favicon-96x96.png
│   │   ├── favicon-192x192.png
│   │   ├── favicon-512x512.png
│   │   ├── apple-touch-icon.png
│   │   └── site.webmanifest
│   ├── css/                      ← Reserved for future stylesheets
│   └── js/                       ← Reserved for future scripts
│
└── media/
    ├── images/                   ← Site-wide images
    │   ├── hero.jpg              ← Home page header photo
    │   ├── leo.jpg               ← Leo's portrait photo
    │   └── logo.jpg              ← Gallina Gardens logo
    │
    ├── case-studies/             ← One image per case study panel
    │   ├── margaret-before-after.jpg
    │   ├── margaret-hedge-work.jpg
    │   ├── margaret-finished.jpg
    │   ├── robert-jean-before.jpg
    │   ├── robert-jean-planting.jpg
    │   ├── robert-jean-after.jpg
    │   ├── dorothy-planting.jpg
    │   ├── dorothy-borders.jpg
    │   └── dorothy-completed.jpg
    │
    └── gallery/                  ← Gallery page images
        ├── lawn-care-falmouth.jpg
        ├── hedge-trimming-penryn.jpg
        ├── planting-mylor.jpg
        ├── pressure-washing-flushing.jpg
        ├── maintenance-mabe-burnthouse.jpg
        ├── lawn-restoration-budock-water.jpg
        ├── containers-falmouth.jpg
        ├── formal-hedging-penryn.jpg
        └── walled-garden-mylor.jpg
```

---

## How to replace images

**To replace any image:**
1. Prepare your new photo — resize it to roughly the same dimensions as the one you are replacing
2. Name it **exactly the same** as the file you are replacing (e.g. `leo.jpg`)
3. Drag it into the correct folder on GitHub, replacing the old file
4. The website updates automatically within 60 seconds

**To add a new gallery image:**
1. Save your photo as a `.jpg` file with a clear descriptive name (e.g. `hedge-trim-mylor-2025.jpg`)
2. Upload it to `media/gallery/`
3. Open `index.html`, find the gallery section (search for `gallery-grid`) and add a new line:
   ```html
   <div class="gallery-item" data-cat="lawn">
     <img src="media/gallery/your-filename.jpg" alt="Description of the photo" loading="lazy"/>
   </div>
   ```
   Change `data-cat` to one of: `lawn`, `hedge`, `pressure`, `planting`, `maintenance`

**To add a new case study:**
- Upload 3 photos to `media/case-studies/` and copy an existing case study block in `index.html`

---

## How to update text content

1. Download `index.html` from GitHub
2. Open it in a text editor (Visual Studio Code recommended — free at code.visualstudio.com)
3. Use **Ctrl+F** to search for the text you want to change
4. Edit it, save the file, and re-upload it to GitHub

---

## Contact form

Forms are handled by **Formspree** and protected by **Google reCAPTCHA v3**.  
Submissions are delivered to: `leo@gallina.me.uk`

If forms stop working, check:
- formspree.io — that the form is active and `gallinagardens.co.uk` is in allowed domains
- google.com/recaptcha/admin — that `gallinagardens.co.uk` is in the allowed domains list

---

## Moving to FastHosts (when domain is ready)

When moving from GitHub Pages to FastHosts web hosting:
1. Upload `index.html`, `send.php`, `media/`, and `assets/` to the `public_html` folder via FTP or File Manager
2. Do **not** upload `CNAME`, `README.md` or `.gitignore`
3. Fill in SMTP credentials in `send.php`
4. The contact forms will then send directly via SMTP instead of Formspree
