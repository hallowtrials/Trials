# Hallow Trials — Landing Page

A responsive, single-page event site for **The Hallow Trials**.
Built with vanilla **HTML/CSS/JS**, optimized for mobile with a sticky header, animated countdown, YouTube teaser embed, and a responsive games gallery.

---

## 🎯 Features

* **Sticky Nav** with quick links: Countdown · Videos · Games
* **Hero Section** with event details card
* **Animated Countdown** to Halloween (20:00 on Oct 31)
* **Responsive YouTube Embed** (no blank space on mobile)
* **Games Grid** (2×2 on tablet/desktop, 1×N on small phones)
* **Accessible Markup** (labels, roles, `aria-*`, reduced motion support)
* **No frameworks** — just fast, portable code

---

## 🗂 Project Structure

```
.
├── Home.html            # The page (all CSS/JS inline)
├── poster.jpg            # Hero/Poster image
├── Silence Room.jpeg     # Game thumbnails
├── Jiangshi.jpeg
├── The Curse.jpeg
├── Three Doors.jpeg
└── ht-removebg-preview.png  # Favicon
```

> Rename image files as needed, but keep the same filenames (or update the `src` paths in `index.html`).

---

## 🚀 Quick Start (Local)

1. Clone or download this repo.
2. Open `Home.html` directly in your browser.

   * Optional: run with a simple static server for better caching/refresh:

     ```bash
     # Python 3
     python -m http.server 8080
     # then open http://localhost:8080
     ```

---

## 🌐 Deploy to GitHub Pages

1. Create a new GitHub repo and push these files.
2. In your repo: **Settings → Pages**

   * **Source:** `Deploy from a branch`
   * **Branch:** `main` (or `master`) → `/ (root)`
3. Save. Your site will be available at:
   `https://<your-username>.github.io/<repo-name>/`

> If images don’t load on Pages, confirm their case-sensitive names match exactly (e.g., `Three Doors.jpeg` vs `three-doors.jpeg`).

---

## ⚙️ Configuration

### Countdown Target

The countdown is calculated in `Home.html`:

```js
function nextHalloween(year){ return new Date(year, 9, 31, 20, 0, 0); } // Oct is month 9 (zero-based)
```

* Timezone uses the visitor’s local time.
* To count down to a custom date/time, change the function above.

### YouTube Video

Update the `iframe` `src` with your own video ID:

```html
src="https://www.youtube.com/embed/oXEOtlU-dAs?si=N0idKdyqvgRc9nei"
```

### Social Links

Footer icons link to YouTube and Instagram. Replace with your own handles if needed.

---

## 📱 Mobile Behavior

* On phones, the header wraps: **brand on row 1**, **3 links on row 2** (always visible).
* The video card **does not stretch**; it maintains 16:9 using `aspect-ratio`.
* Games grid becomes **single column** on small screens (`≤480px`).

---

## 🧰 Tech Stack

* **HTML5** for structure
* **CSS3** (custom properties, `aspect-ratio`, responsive media queries)
* **JavaScript** (vanilla for countdown animation)

No build tools, no dependencies.

---

## 🔎 Accessibility & Performance

* Reduced motion respected via `@media (prefers-reduced-motion: reduce)`.
* Semantic elements (`header`, `nav`, `section`, `figure`, `footer`) and ARIA labels.
* Lazy-loaded images (`loading="lazy"`).
* Color contrast tuned for dark theme.

---

## 🧩 Customization Tips

* Colors are centralized in `:root` CSS variables:

  ```css
  :root{
    --bg:#0a0a0f; --bg-2:#0f0a12; --ink:#e6e3ff; --ash:#9a94b8;
    --blood:#b10f2e; --ecto:#6b4dff; --card:#121018; --max:1400px;
  }
  ```
* Swap the **Cinzel** & **Inter** fonts in the `<head>` if you prefer others.
* Replace `poster.jpg` and game thumbnails with your event assets.

---

## 🐞 Troubleshooting

* **Large blank space below the video on mobile?**
  Fixed by preventing flex growth on the video card and enforcing `aspect-ratio: 16/9` within mobile media queries.
* **Links wrap or overflow?**
  The mobile nav uses two rows by design. If you need one-row mobile nav, shorten the brand text or reduce font size in the `≤480px` media query.

---

## 🙌 Credits

* **Event:** School of Foundation & Visual Cinematography Club
* **Design/Coding:** *ASH* (see footer link)
* Icons: Inline SVGs

---

## 📄 License

MIT License — feel free to use and adapt.
Please replace logos/images with assets you have rights to use.

---

## ✨ Contributing

PRs welcome for bug fixes and accessibility improvements.
For major changes, open an issue first to discuss what you’d like to change.

---

**Happy haunting!** 🦇
