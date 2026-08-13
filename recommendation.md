# Recommendations — edmunxx.github.io

## Priority 1 — Critical (fix now)

### 1.1 Optimize the hero background image
- `hero-bg.jpg` is **~3.9 MB** — this is the single largest file and the first thing visitors load.
- **Action**: Convert to WebP (target <500 KB) using Squoosh, TinyPNG, or similar. Replace `hero-bg.jpg` and update the CSS reference.
- **Impact**: Reduces initial load time significantly, especially on mobile.

### 1.2 Fill in meta tags
- `<meta name="description">` and `<meta name="keywords">` are **empty** on all pages.
- **Action**: Add a compelling description (e.g. "Edmundo Ferdinandus — UI/UX Designer & Web Developer based in Jakarta") and relevant keywords. This is critical for SEO.
- **Impact**: Improves search engine visibility and social media preview cards.

### 1.3 Remove unused pages
- `inner-page.html` and `portfolio-details.html` contain **untouched template placeholder content** and serve no purpose.
- **Action**: Delete both files, or replace them with actual content if they're needed.
- **Impact**: Cleaner repo, no confusing dead links.

### 1.4 Update footer attribution
- Footer still reads *"Copyright Lonely — Designed by BootstrapMade"*.
- **Action**: Replace with your own name and a brief credit line. The free template license requires attribution, but you can reword it to say *"Template originally by BootstrapMade, customized by Edmundo Ferdinandus"*.
- **Impact**: Professional appearance; avoids confusion.

---

## Priority 2 — Important (should fix)

### 2.1 Remove dead JavaScript/CSS dependencies
The following libraries are loaded but their features are **not used** on `index.html`:
- **Isotope** — portfolio filter JS loaded, but portfolio section removed
- **GLightbox** — lightbox JS loaded, but no lightbox elements in HTML
- **Swiper** — loaded for testimonials, but testimonials section removed
- **PureCounter** — loaded, but no counter elements in HTML
- **PHP Email Form** — validate.js loaded, but contact.php is a placeholder

**Action**: Remove the corresponding `<link>` and `<script>` tags from `index.html`. This will reduce page weight and improve load performance.

### 2.2 Fix the contact form
- `forms/contact.php` points to `contact@example.com` and requires a PHP library that isn't present.
- **Action**: Since GitHub Pages is static-only, replace the PHP form with a service like **Formspree**, **Getform**, or **Netlify Forms**. At minimum, add a `mailto:` action or embed a Google Form.
- **Impact**: Visitors can actually reach you through the site.

### 2.3 Add a Portfolio section
- You have **9 portfolio images** in `assets/img/portfolio/` but no portfolio section on the site.
- **Action**: Re-add a portfolio grid to `index.html`. Even a simple CSS grid with your 9 projects would strengthen the portfolio significantly. Restore Isotope for filtering if needed.
- **Impact**: The #1 thing recruiters look for — a visible portfolio.

### 2.4 Compress all images
- Beyond the hero image, check portfolio and testimonial images. Unoptimized JPEGs are common.
- **Action**: Run all images through an optimizer (Squoosh, ImageOptim, or a GitHub Actions pipeline).
- **Impact**: Faster page loads across the board.

---

## Priority 3 — Nice-to-have (quality of life)

### 3.1 Add a favicon that matches your brand
- Current favicon (`favicon.png`) is the template default.
- **Action**: Create a custom favicon using your initials or a simple icon. Also update the Open Graph meta tags for social sharing.
- **Impact**: Professional branding.

### 3.2 Add Open Graph / Twitter Card meta tags
- **Action**: Add `<meta property="og:title">`, `<meta property="og:description">`, `<meta property="og:image">`, and Twitter card tags.
- **Impact**: Better preview when your link is shared on social media.

### 3.3 Add a proper 404 page
- GitHub Pages supports custom 404 pages.
- **Action**: Create `404.html` with a friendly message and navigation back to the homepage.
- **Impact**: Better UX for anyone who lands on a broken link.

### 3.4 Add a sitemap and robots.txt
- **Action**: Create `sitemap.xml` and `robots.txt` in the root. Submit to Google Search Console.
- **Impact**: Improves SEO and crawlability.

### 3.5 Consider a dark mode toggle
- **Action**: Add a simple CSS dark mode using `prefers-color-scheme` or a manual toggle with `data-theme` attribute.
- **Impact**: Modern expectation for personal sites; shows design awareness.

### 3.6 Add structured data (JSON-LD)
- **Action**: Add `Person` schema markup with your name, profession, social profiles, and email.
- **Impact**: Rich snippets in search results.

### 3.7 Set up CI/CD with GitHub Actions
- **Action**: Add a workflow that runs a linter (HTMLHint) and image optimizer on push.
- **Impact**: Automated quality checks; catches issues before they go live.

---

## Summary Table

| # | Recommendation | Priority | Effort | Impact |
|---|---------------|----------|--------|--------|
| 1.1 | Optimize hero-bg.jpg to WebP | Critical | Low | High |
| 1.2 | Fill in meta description & keywords | Critical | Low | High |
| 1.3 | Remove unused HTML pages | Critical | Low | Medium |
| 1.4 | Update footer attribution | Critical | Low | Medium |
| 2.1 | Remove dead JS/CSS dependencies | Important | Medium | High |
| 2.2 | Fix contact form (Formspree/etc.) | Important | Medium | High |
| 2.3 | Add Portfolio section with images | Important | Medium | Very High |
| 2.4 | Compress all images | Important | Low | Medium |
| 3.1 | Custom favicon | Nice-to-have | Low | Low |
| 3.2 | Open Graph meta tags | Nice-to-have | Low | Medium |
| 3.3 | Custom 404 page | Nice-to-have | Low | Low |
| 3.4 | Sitemap + robots.txt | Nice-to-have | Low | Medium |
| 3.5 | Dark mode | Nice-to-have | Medium | Medium |
| 3.6 | JSON-LD structured data | Nice-to-have | Low | Medium |
| 3.7 | GitHub Actions CI/CD | Nice-to-have | Medium | Low |

**Top 3 to start with**: (1) Optimize hero image, (2) Add Portfolio section, (3) Fix meta tags. These three give you the biggest visible improvement for the least effort.
