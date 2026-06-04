# Abitur | DIA — Bilingual Website
**Modern, clean, professional website highlighting the benefits of the German Abitur (including the German International Abitur / DIA)**

For students (14–19) and parents at German international schools (Deutsche Auslandsschulen) in Asia.

This is a **simple, fully static, self-contained website** built with:
- HTML5
- Tailwind CSS (via CDN – no build step)
- A small amount of clean vanilla JavaScript

Created as a first project: easy to understand, easy to edit, and ready to use on school websites or at information events.

---

## What the Site Contains

- **Fully bilingual** (English + German) with a prominent, reliable language switcher (EN / DE)
- **German identity**: Official German flag (black-red-gold) integrated in logo, navigation, and footer + multiple references and badges for ZfA (Zentralstelle für das Auslandsschulwesen) and Deutsche Auslandsschulen
- **New comparison section**: Clear, balanced side-by-side comparison of Abitur/DIA vs. the International Baccalaureate (IB) — the main competing qualification — with emphasis on Germany university access, costs, language advantage, and career fit
- **Synthetic photos**: Four high-quality generated images of happy, diverse students at German international schools in Asia, used in the hero, testimonials, and a new "Student life" photo strip in the Schools in Asia section
- **Clear navigation**: Home (hero), For Students, For Parents, Why Abitur Today, German Schools in Asia, Contact
- **Hero section** with strong bilingual headline and CTAs
- **Dedicated sections** for students and parents with benefit cards
- **Relevance in Asia** section with key facts and statistics
- **German Schools in Asia** overview + link to the official ZfA world map
- **Placeholder testimonials** (clearly marked as examples — replace with real ones)
- **Working contact form** (demo mode — shows success message)
- **Download buttons** that actually work (generate a small text file as placeholder)
- **Professional, trustworthy design** using deep blue + emerald green + clean whites
- **Fully responsive** (excellent on phone, tablet, and desktop)
- **Accessible** markup and keyboard-friendly

---

## Project Structure

```
Abitur-Website/
├── index.html                          ← The complete website (all content + design + JS)
├── README.md                           ← This file (instructions + editing guide)
└── assets/
    ├── images/                         ← Empty – add real photos here later
    └── downloads/
        └── abitur-information-brochure-placeholder.txt   ← Placeholder for real PDF
```

Only **two main files** to maintain at the beginning. Perfect for a first project.

---

## How to Preview / Run the Website Locally (Windows)

### Easiest way (no installation)
1. Open **File Explorer**
2. Go to your folder: `C:\Users\akama\Documents\Abitur-Website`
3. Double-click **`index.html`**
4. It opens directly in your default browser (Edge, Chrome, etc.)

Everything works: language switching, buttons, cards, mobile menu.

### Recommended for development (with live reload)
1. Open the folder in **Visual Studio Code**
2. Install the free extension **"Live Server"** by Ritwick Dey (very popular and safe)
3. Right-click on `index.html` → **"Open with Live Server"**
4. The site opens in a browser tab and **automatically refreshes** every time you save changes.

### Using PowerShell / Terminal (built-in, no extra software)
Open PowerShell in the project folder and run:

```powershell
python -m http.server 8000
```

Then visit: `http://localhost:8000`

(Python is pre-installed on most modern Windows machines.)

### Mobile testing
- Use your browser’s developer tools (press **F12**)
- Click the small phone/tablet icon to simulate different screen sizes

---

## How the Language Switcher Works (and How to Edit Text)

All text lives in **one place** — a JavaScript object called `translations` near the bottom of `index.html`.

### To change or translate text:
1. Open `index.html` in any text editor or VS Code.
2. Search for `const translations = {`
3. You will see two big blocks:
   - `en: { ... }` → all English text
   - `de: { ... }` → all German text
4. Find the key you want to change (they are named clearly, e.g. `"students.benefit1.title"`).
5. Edit the text inside the quotes.
6. Save the file and refresh the browser.

### Adding a new translatable section
1. Add `data-i18n="new.unique.key"` to the HTML element.
2. Add the same key + English text inside the `en` object.
3. Add the same key + German text inside the `de` object.

Example:
```html
<h3 data-i18n="newsection.title">New Title</h3>
```

Then in the translations object:
```js
en: {
  "newsection.title": "New Title Here",
  ...
},
de: {
  "newsection.title": "Neuer Titel hier",
  ...
}
```

The language system automatically updates everything when the user clicks EN or DE.

**Tip**: Your choice is saved in the browser (localStorage), so it remembers the language on the next visit.

---

## How to Customize Further (Made Simple for Beginners)

- **Colors**: Look for the Tailwind config script in the `<head>`. You can change the brand colors there or just edit classes like `text-[#1e3a8a]` directly.
- **Add real photos**: Replace placeholder `<div class="...">` avatar blocks or hero visual areas with real `<img src="assets/images/your-photo.jpg">` tags. Create good filenames.
- **Change the "Download" behavior**: Currently it uses JavaScript to create a small text file. Later replace the `onclick="downloadBrochure()"` attributes with normal links pointing to a real PDF in the `assets/downloads/` folder.
- **Contact form**: Currently shows a success message only. To make it send real emails, connect it to a free service like Formspree, Netlify Forms, or your school’s email system.
- **Add more testimonials**: Copy one of the existing testimonial cards and update the `data-i18n` keys + the translations object.
- **New language (e.g. Chinese)**: Duplicate the structure, add a third button, and extend the `setLanguage` function. It’s very doable once you’re comfortable.

---

## Recommended Next Improvements (After You’re Comfortable)

- Replace example testimonials with real quotes + photos from your school community.
- Add 2–4 beautiful photos (diverse students, classroom, graduation, Asia + Germany feel).
- Create or commission a real 4–6 page PDF brochure and link to it.
- Add your specific school name/logo in the header/footer.
- Add a small FAQ section (easy to do with Tailwind).
- Host it for free on GitHub Pages, Netlify, or Vercel (drag & drop the whole folder).

---

## Official Links Included (Already in the Site)

- ZfA – Deutsche Auslandsschulen: https://www.auslandsschulwesen.de/
- PASCH Initiative: https://www.pasch-net.de/
- DAAD – Study in Germany
- anabin recognition database (important for university admissions)

Always direct families to the official sources for the latest details.

---

## Credits & Accuracy

Content is based on publicly available information from:
- Zentralstelle für das Auslandsschulwesen (ZfA)
- Official descriptions of the German International Abitur (DIA)
- Reliable sources on university entrance qualifications and costs in Germany

The site is designed to be **inspiring and accurate** while remaining easy to maintain. Always verify the latest facts with the ZfA and your school.

---

## Questions?

This site was built step-by-step as a first project. The code is intentionally clean and heavily commented in the JavaScript section.

Feel free to open `index.html` and explore. The most important part for future editing is the `translations` object.

Enjoy building and sharing this with your school community!

---

**Created with care for German international education in Asia.**