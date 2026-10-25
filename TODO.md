# Website to-do list

Reviewed from the uploaded folder (current version only; `v1/` was skimmed for size). Tick things off as you go. Items marked **(quick)** take under 10 minutes.

**Suggested order:** 1 (bugs) > 2 (images) > 3 (content) > 5 (navigation) > 6 (layout) > 7 to 9 (polish) > 10 (deploy).

---

<details><summary><b>Completed</b></summary>

## 1. Bugs and mistakes in the code

- [x] **(quick)** `<title>` still says "website title (will change later)". Make it e.g. `Bedrijfsnaam | Montage en maatwerkinterieur in [plaats]`.
- [ ] **(quick)** `href="#LINKHERE"` on the "Bekijk mijn werk" button goes nowhere. Point it at `#services` (or a gallery section/page once it exists).
    - [ ] Add galery page
- [x] **(quick)** Every service card uses `<h1>`. A page should have exactly one `<h1>`. Change the card titles to `<h2>` (or `<h3>` under a section heading), and the about heading too.
- [x] **(quick)** `transition-duration-0.5` is not a Tailwind class, so it does nothing. Use `duration-500` (or `duration-300`).
- [x] **(quick)** `Badkamer & toilet` should be `Badkamer &amp; toilet` in HTML.
- [x] **(quick)** `.gitignore` lists `package*.json`, `src/input.css`, `.gitignore` and `.prettierrc`. That means your Tailwind source and package files are not in the repo, so nobody (including future you) can rebuild the CSS from GitHub. Keep only `node_modules/` in it, then `git add` the missing files.
- [x] **(quick)** `package.json` name is `dad's-website`. The apostrophe is not valid for an npm name. Rename to `business-website`.
- [x] ~~**(quick)** Remove the placeholder `"test"` script from `package.json` and add real scripts (see section 11).~~
- [x] The empty comments at the top of `<body>` (`NAV`, `marker for navbar verticallizer`) describe a navbar that no longer exists. Build it or delete the comments.
- [x] `src/output.css` is not minified (about 17 KB). Build with `--minify` for production.
- [x] ~~Check there is no leftover unused CSS or class strings from v1 in the Tailwind version.~~

---

## 2. Images (biggest performance win)

Current sizes: `welcome-impression.jpg` is **7.3 MB** (6000x4000), and the three service photos total **2.5 MB** (up to 5920x3947). The page is roughly 10 MB for a three-section site. On a phone connection that is several seconds of blank space.

- [x] Resize the welcome image to about 1600 px wide (the displayed size is at most 600 px, so 1200 to 1600 covers high-DPI screens).
- [x] Resize service photos to about 800 px wide.
- [x] Convert to **WebP** (or AVIF) at roughly quality 75 to 80. Target: under 150 KB each.
- [x] ~~Offer multiple sizes with `srcset` and `sizes`, so phones download the small version.~~
- [x] ~~Add `width` and `height` attributes to every `<img>` to stop layout shift while loading.~~
- [x] ~~Add `loading="lazy"` to everything below the fold (services, about). Do **not** lazy-load the welcome image; it is the main visual, so give it `fetchpriority="high"`.~~
- [ ] **(Later)** Strip EXIF metadata from photos (location data can leak from phone photos, and it adds weight).
- [ ] **(Later)** Optimise the PNGs too: `logo-square.png` is 500x500, which is more than needed. An **SVG** logo would be sharper and smaller if your dad has the source file.
- [ ] **(Later)** Replace stock photos with real photos of your dad's work (see section 3).
- [x] Keep original full-size photos outside the repo (or use Git LFS) so the repo stays small. The repo is already about 21 MB of `.git` history from v1 images.

---
</details>
## 3. Content (the site cannot go live without this)

- [ ] Replace **all lorem ipsum**: three service descriptions, and the contact paragraph.
- [ ] Replace placeholders: `mail@domain.ext`, `+31 6 00000000`, `Bedrijfsnaam`, `KvK 00000000`.
- [ ] Real photos of finished work (kitchens, bathrooms, furniture). Before and after shots work well.
- [ ] A real photo of your dad for the about section (a person's face builds trust far more than a stock image). The `alt` text should name him.
- [ ] Decide whether the real first name goes on the site ("Hallo, ik ben Jan" currently). Customers like it.
- [ ] Write the service text in specifics: what is included, typical project size, materials, how long a job takes. Example: "Keuken geplaatst in 2 tot 3 dagen, inclusief aansluiten van apparatuur."
- [ ] Add the **area served** ("Werkgebied: Utrecht en omgeving").
- [ ] Add **opening hours** or "bereikbaar" times and a response promise ("Reactie binnen 1 werkdag").
- [ ] Add 2 to 4 **customer reviews** with first name and place (ask permission). A Google Reviews link works too.
- [ ] Add a short **"Hoe werkt het"** section: 1) kennismaking en opmeten, 2) offerte, 3) uitvoering, 4) oplevering.
- [ ] Add a call to action to **request a quote** ("Vraag vrijblijvend een offerte aan"), not only "Kom in contact".
- [ ] Add experience/certifications if they exist (the `<!-- experience (later) -->` comment). Examples: diplomas, brand partners, insurance, guarantee ("garantie").
- [ ] Have someone proofread all Dutch text. Make the tone consistent (je/u, ik/wij). Currently the site uses "ik" (sole trader); keep that throughout.
- [ ] Decide on the **gallery** (see section 4).

---

## 4. Gallery / "Mijn werk"

The button says "Bekijk mijn werk", but there is currently nothing to look at. The v1 gallery was marked as non-working.

- [ ] Decide: a section on the home page (simplest, recommended) or a separate `gallerij/` page.
- [ ] Build a simple responsive grid (CSS grid, `grid-cols-2 md:grid-cols-3`), with `object-cover` and a fixed aspect ratio.
- [ ] Optional: a lightbox for enlarged photos. Keep it accessible (close with Esc, focus trap, `alt` text). Or skip JavaScript entirely and link to the full image.
- [ ] Use properly sized thumbnails and lazy-loading (section 2).
- [ ] Group by category if there are many (Keuken, Badkamer, Maatwerk).
- [ ] Delete the v1 gallery photos. They include desktop wallpapers (`dolomite-dreams...`, `firewatch...`) that are not your dad's work and are probably copyrighted.

---

## 5. Navigation

There is currently **no navbar** in the code, although the README says there is one.

- [ ] Decide whether you need one. For a one-page site with four sections, a slim sticky header with the logo and a "Bel nu" button is enough. This also fixes the mobile "how do I call?" problem.
- [ ] Mobile: no hamburger menu needed if the nav is 3 to 4 short links; let them wrap or scroll, or hide them and keep only the call button.
- [ ] Add `scroll-smooth` on `<html>` and `scroll-mt-*` on each section so the sticky header does not cover headings.
- [ ] Highlight the active section using `IntersectionObserver` (not scroll-position maths). Add `aria-current="true"` to the active link.
- [ ] Add a skip link ("Ga naar inhoud") as the first focusable element.
- [ ] Wrap the logo in a link to `#top`.
- [ ] Add a "back to top" link in the footer (optional).
- [ ] Respect `motion-reduce:` for smooth scroll and animations.

---

## 6. Layout and responsiveness

Your README says desktop looked bad at one point, and the about section on tablet landscape is a known problem.

- [ ] Test at **320, 375, 768, 1024, 1280, 1440 and 1920 px** wide, plus phone landscape. Fix anything that overflows or stretches.
- [ ] Add one shared page container (`mx-auto max-w-6xl px-8 md:px-15`) and use it for every section, instead of repeating `mr-8 ml-8 md:mr-15 md:ml-15` on each. On very wide screens, the content currently stretches edge to edge.
- [ ] Welcome section: the image is hidden below `md` (`max-md:hidden`), so phone visitors see only a logo, heading and button. Consider showing a cropped version of the photo on mobile as well.
- [ ] Welcome logo is `size-50` (200 px). It sits large above the heading and pushes content down on small screens. Consider a smaller logo in a header and a heading-first hero.
- [ ] Fixed pixel-ish widths: `w-100 shrink-0` on the hero text column can overflow on screens narrower than 400 px plus margins. Use `w-full max-w-md` or similar.
- [ ] Services cards: fixed `md:h-60 md:w-90` on images makes them awkward at some widths. Use `aspect-[4/3] w-full` and let the grid decide width.
- [ ] Use CSS grid (`grid md:grid-cols-3 gap-4`) for the services instead of the flex mix.
- [ ] **About section on tablet landscape:** try `md:grid md:grid-cols-[15rem_1fr]` with the image `aspect-[4/5]`, and cap paragraph width at `max-w-prose`. Narrow text columns look worse than wide ones, not better.
- [ ] Contact section: the grid with `lg:contents` and `lg:row-span-2` is clever but fragile. Simplify to a two-column grid, with the footer text as a separate `<footer>` element.
- [ ] Use `min-h-dvh` (not `100vh`) if you add any full-height section, so mobile browser toolbars do not cut it off.
- [ ] Check long Dutch words ("Maatwerkinterieur", "Keukenmontage") on a 320 px screen. Add `hyphens-auto` and `lang="nl"` (already set) or `break-words`.
- [ ] Test with browser zoom at 200% and with the text size increased.
- [ ] Test dark mode behaviour: either force a light colour scheme (`color-scheme: light`) or design for dark. Right now it is undefined.

---

## 7. Design polish

- [ ] **Hover effect:** `hover:scale-115` on buttons is very large (15% growth) and will overlap neighbouring content. Use `hover:scale-105` or change colour/background instead.
- [ ] Add `focus-visible:` styles to every link and button (outline or ring). Do not rely on browser defaults on a dark background.
- [ ] Add `active:` state for buttons (touch feedback).
- [ ] Make the two CTA buttons a proper reusable style, since they are copied twice (one `@apply`-free option: a small Tailwind component class in `input.css` via `@layer components`).
- [ ] Define a design scale in `@theme`: spacing for sections (`py-16` consistently), a heading scale, and one accent colour. Currently the colour palette is only `#111` and `#fff`, which feels plain for a craft business. A warm wood/neutral accent would help.
- [ ] Use Montserrat weights deliberately: you load 100 to 900 variable, but probably use three weights.
- [ ] Add a subtle section divider or background change (`bg-neutral-50`) between services and about, so the page does not blur together.
- [ ] Give the service cards a hover state (image zoom within `overflow-hidden`, or a shadow), but only if they link somewhere. If they do not, do not make them look clickable.
- [ ] Align heading sizes: services use `text-2xl` to `md:text-3xl`; about uses `text-3xl`; contact uses `text-3xl`. Pick a scale.
- [ ] Add a section heading above the services ("Wat ik doe") so the cards have context.
- [ ] Check the contrast of the borders (`border` default is light grey and can disappear).
- [ ] Review the contact section: the white-on-dark outlined links look like buttons. Make them larger tap targets (min 44 px tall).

---

## 8. Accessibility

- [ ] All service images, the welcome image and the about photo currently have `alt=""`. That marks them as decorative, which is wrong for content photos. Write real descriptions, e.g. `alt="Op maat gemaakte keuken met eiken fronten"`. Keep `alt=""` only for truly decorative images.
- [ ] Logo `alt` is "Vierkant logo". Use the company name: `alt="Bedrijfsnaam"`.
- [ ] Use landmarks: `<header>`, `<nav>`, `<main>`, `<footer>`. At the moment everything sits straight in `<body>`, and the footer text is inside the contact `<section>`.
- [ ] Give each `<section>` an `aria-labelledby` pointing to its heading.
- [ ] Heading hierarchy: one `<h1>`, then `<h2>` per section, `<h3>` for cards.
- [ ] Icon-only or icon-decorated links: add `aria-hidden="true"` to the Font Awesome `<i>` icons so screen readers skip them.
- [ ] Tap targets at least 44x44 px for phone and email links.
- [ ] Check contrast of every text and background pair (aim for 4.5:1). Run axe DevTools or Lighthouse.
- [ ] Test with keyboard only (Tab, Shift+Tab, Enter) and with a screen reader (VoiceOver or NVDA) once.
- [ ] Test at 200% zoom and in Windows high-contrast mode.
- [ ] Respect `prefers-reduced-motion` for all transitions.

---

## 9. Fonts and icons

- [ ] **Self-host Montserrat** instead of loading it from Google. Using Google Fonts remotely sends visitors' IP addresses to Google, and a German court ruled that this breached GDPR (Munich, 2022). The Dutch situation is less tested, but self-hosting is also faster and removes a third party. Use `fontsource` (`npm i @fontsource-variable/montserrat`) or download the woff2 files. Load only the weights and Latin subset you need, with `font-display: swap`, and preload the main file.
- [ ] **Remove the Font Awesome kit script.** It loads a JavaScript file from a third party (account-bound, render-blocking, and again a privacy concern) just for three icons (arrow, at, phone). Replace with inline SVG (Heroicons, Lucide or Tabler, all free) or Unicode.
- [ ] After removing both, there are no external requests, so no cookie or data-transfer worries from the site itself.
- [ ] Favicon: add proper sizes (`favicon.ico`, 32x32 and 16x16 PNG, `apple-touch-icon.png` 180x180, and ideally an SVG favicon). A 500 px PNG as the only icon is not ideal.
- [ ] Add a `site.webmanifest` with theme colour (optional, small win).

---

## 10. Contact and forms

Right now the contact options are just a `mailto:` link and a phone number. That is fine for a start but loses people without a mail app configured (many people use webmail).

- [ ] Keep the phone link prominent. For a tradesperson, a phone call is the main conversion. Make it a button on mobile.
- [ ] Add a **WhatsApp link** (`https://wa.me/31...`). Popular in NL for quotes, and customers can send photos of the room.
- [ ] Add a **contact/quote form** (name, email, phone, short description, optional photo upload). On mijn.host (PHP is available on their shared hosting, as far as I know; verify in your plan), a small PHP script works. Otherwise use a form service.
- [ ] If you build the PHP form: validate and sanitise input server-side, add a **honeypot** field and basic rate limiting, send with proper headers, and never put user input into mail headers unescaped (header injection). Consider **Cloudflare Turnstile** or hCaptcha if spam appears.
- [ ] Add a confirmation message (and a "bedankt" state) and a clear error message in Dutch.
- [ ] Use `autocomplete` attributes (`name`, `email`, `tel`) and the right `type` and `inputmode`, so phones fill it in.
- [ ] Add a labelled field for every input (no placeholder-only labels).
- [ ] Set up the business email address on the domain, and configure **SPF, DKIM and DMARC** in DNS, so form emails do not land in spam.
- [ ] Add a **Google Maps link** or embedded map for the address, but only if the business receives visitors. An embedded map loads Google scripts and cookies, so prefer a plain link or a static image.
- [ ] Replace "Contact opnemen kan via de mail of door te bellen" with specific wording and an expected response time.
- [ ] Mention that a quote is free and non-binding ("gratis en vrijblijvend") if true.

---

## 11. Legal and business information (Netherlands)

Check these with your dad or an accountant; I am not a lawyer.

- [ ] Show the **company name, address, KvK number, BTW number and email address** on the site. Dutch law requires webshops and businesses with a website to be identifiable. Put it in the footer.
- [ ] Add a **privacy statement** page (AVG/GDPR) as soon as there is a contact form or any analytics. It states what you collect, why, how long you keep it, and the contact for requests.
- [ ] Add **general terms** (algemene voorwaarden) if your dad uses them for quotes. Link them in the footer.
- [ ] No tracking cookies means **no cookie banner needed**. Keep it that way: no Google Analytics, no embedded YouTube/Maps, no social widgets. If you want statistics, use a cookieless tool (Plausible, Simple Analytics, or Matomo without cookies).
- [ ] Photos of customers' homes: make sure customers agree before publishing, and avoid showing house numbers, family photos or anything personal.
- [ ] Check the licences of any photos or fonts you did not make. Stock photos need attribution or a licence. The v1 wallpapers must go.
- [ ] Add an accessibility statement only if required (usually not for a small business).

---

## 12. SEO and findability

- [ ] Unique, specific `<title>` (about 50 to 60 characters) and `<meta name="description">` (about 150 characters), in Dutch, with the trade and the region.
- [ ] Add `<link rel="canonical" href="https://[domein]/">`.
- [ ] Open Graph and Twitter card tags (`og:title`, `og:description`, `og:image` (1200x630), `og:locale="nl_NL"`) so links look right on WhatsApp and Facebook.
- [ ] **`LocalBusiness` JSON-LD** structured data (name, address, phone, area served, opening hours, logo, social links).
- [ ] `robots.txt` and `sitemap.xml`.
- [ ] Use words customers search for in headings and text: "keukenmontage [plaats]", "badkamer plaatsen", "maatwerk kast". Do not stuff keywords.
- [ ] Create and fill in a **Google Bedrijfsprofiel** (Business Profile). For local trades this brings more customers than the website itself.
- [ ] Register with Bing Places (optional) and local directories (Werkspot, Trustoo, Marktplaats-style pages, depending on the trade).
- [ ] Set up Google Search Console and submit the sitemap.
- [ ] Ask happy customers for Google reviews and link to them from the site.
- [ ] Make sure the domain redirects `www` to non-`www` (or the reverse), consistently.

---

## 13. Performance targets

- [ ] Run **Lighthouse** (mobile) and aim for 90+ on Performance, Accessibility, Best Practices and SEO.
- [ ] Largest Contentful Paint under 2.5 s on a mid-range phone on 4G.
- [ ] No layout shift (set image dimensions, reserve space for fonts).
- [ ] Total page weight under about 500 KB once images are optimised.
- [ ] Enable Brotli or gzip compression on the server (see section 14).
- [ ] Long-lived caching for images, fonts and CSS, with a changed filename (or `?v=`) when you update them.
- [ ] Test on a real mid-range Android phone, not only desktop dev tools.

---

## 14. Deployment on mijn.host

I do not have your hosting plan details, so check the points below against your control panel.

- [ ] Register or point the **domain** and set up DNS (A record, `www` CNAME, mail records).
- [ ] Enable **HTTPS** (a free Let's Encrypt certificate is usually available in the control panel), then force it.
- [ ] Upload only the built files via SFTP or the file manager: `index.html`, `assets/`, `src/output.css` (or better, move the built CSS to `assets/css/`). Do **not** upload `node_modules`, `.git`, `v1/` or source files.
- [ ] Create an `.htaccess` (if the server runs Apache) that: redirects HTTP to HTTPS, redirects `www` to the chosen host name, enables compression, sets cache headers, and defines a custom 404 page.
- [ ] Add a custom **404 page** in Dutch with a link back home.
- [ ] Add basic security headers where possible (`X-Content-Type-Options`, `Referrer-Policy`, `Content-Security-Policy`). With self-hosted fonts and no scripts, a strict CSP is easy.
- [ ] Decide how future updates get deployed: manual SFTP upload, or a GitHub Action that uploads via SFTP/FTPS on each push to `master`. Even a simple script that builds and uploads saves mistakes.
- [ ] Set up **backups** (host backups and the Git repo).
- [ ] Make a test deployment on a subdomain or a temporary URL and test it on phone and desktop before pointing the real domain at it.
- [ ] Do a final check after going live: links, forms, mail delivery, mobile layout, HTTPS padlock, redirects.

---

## 15. Code quality and project hygiene

- [ ] Add scripts to `package.json`:
  - `"dev": "tailwindcss -i ./src/input.css -o ./src/output.css --watch"`
  - `"build": "tailwindcss -i ./src/input.css -o ./dist/style.css --minify"`
- [ ] Consider a `dist/` folder (or `public/`) containing exactly what gets uploaded. The repo root currently mixes source, build output and v1.
- [ ] **Delete `v1/`** (about 34 MB). It stays in git history if you ever want it back. If you need to shrink the history too, use `git filter-repo`, but only if the repo size really matters.
- [ ] Move `README.md` devlogs to a separate `DEVLOG.md` and write a short real README: what the project is, how to run it, how to build and deploy.
- [ ] Add a repo description and topics on GitHub.
- [ ] Add `prettier` scripts (`"format": "prettier --write ."`). You already have the Tailwind plugin installed.
- [ ] Repeated card markup (three service cards) is fine for now. If it grows, generate from a small data list or use an HTML partial/static site generator (Eleventy, Astro) so content changes do not mean editing long class strings.
- [ ] Keep text content (Dutch copy) easy to find, so your dad or you can edit it later without touching the classes.
- [ ] Validate the HTML at validator.w3.org once.
- [ ] Commit small and often, with clear messages. Tag the first live version (`v1.0.0`).
- [ ] If you leave the Claude-generated bits (carousel JS, nav JS) in any file, make sure you understand them or remove them. Unused code is a liability.

---

## 16. After launch

- [ ] Ask your dad to proof the live site and send photos and reviews as they come in.
- [ ] Check the contact form (and the phone number) work monthly. A broken form silently loses customers.
- [ ] Add new project photos to the gallery regularly. A site that never changes looks abandoned.
- [ ] Review Search Console after a month: which searches bring people, and which pages do not get found.
- [ ] Renew checks: domain renewal date, SSL certificate (auto-renew), hosting plan.
- [ ] Update dependencies (`npm outdated`) now and then. Tailwind is only a build tool, so there is no security risk on the live site itself.

---

## Open questions for your dad

1. Real business name, address (or only area served), KvK number and BTW number: which of these should be public?
2. Which services should be listed? Are the three current ones (keuken, maatwerk, badkamer) complete?
3. Does he want a contact form, or only phone and email?
4. Can he provide real photos (and permission from the customers)?
5. Does he already have a logo source file (SVG, AI, PDF)?
6. Does he want prices, "vanaf" prices, or no prices on the site?
7. Which area does he work in, and does he want to be found there on Google?
8. Does he have existing reviews (Google, Werkspot, Facebook) that can be linked?