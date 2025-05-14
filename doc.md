
# IT-project-A-5 Documentation

<div align="center">
<img src="images/logo.png" alt="5*A Ecommerce Logo" width="150px"/>
<h2>Team 5*A - E-commerce Project</h2>
<h3>Modern Online Shopping Platform for Fashion & Accessories</h3>
</div>

---

## Table of Contents

1. [Project Overview & Story](#1-project-overview--story)
2. [Fact-Finding & User Interviews](#2-fact-finding--user-interviews)
3. [Requirement Analysis](#3-requirement-analysis)
4. [Planning & Methodology](#4-planning--methodology)
5. [Design & Diagrams](#5-design--diagrams)
6. [Implementation](#6-implementation)
7. [Testing, Deployment & Maintenance](#7-testing-deployment--maintenance)
8. [Comprehensive Project Files & Folders Guide](#8-comprehensive-project-files--folders-guide)
9. [Development Team & Technical Roles](#9-development-team--technical-roles)
10. [Feature Breakdown](#10-feature-breakdown)
11. [Deployment & Running](#11-deployment--running)
12. [Developer FAQ](#12-developer-faq)
13. [Code Quality, Security & Accessibility](#13-code-quality-security--accessibility)
14. [Contribution Guidelines](#14-contribution-guidelines)
15. [Changelog & Future Directions](#15-changelog--future-directions)

---

## 1. Project Overview & Story

Shopping for fashion, accessories, and shoes should be quick and enjoyable—not stressful! Team 5*A’s mission is to create an engaging, visually rich, and feature-complete e-commerce experience geared toward trendy young users. Our inspiration came from the clutter and limitations of current online fashion stores. We imagined a **modular, maintainable solution** that is easy for groups to improve and extend.

**Key Project Values:**
- **Rapid, intuitive navigation** for all shoppers, with minimal clicks to desired products.
- **Personalization:** Shopping experience is tailored through wishlists and carts, all stored on the client side—no login needed for basic features.
- **Component-based structure:** Each key feature (cart, wishlist, product galleries, feedback, policies) is built as a standalone part, easily editable, with minimal tight coupling.
- **Accessibility by default:** All navigation, content, and popups are tested for keyboard and screen-reader accessibility; critical ARIA and alt tags are included.
- **Effortless onboarding:** New contributors can immediately find and edit their area (HTML, JS, CSS, images, docs) due to directory and code clarity.
- **Responsiveness and style:** The UI is mobile-first, using a combination of modular CSS in `/Style/` and global resets. Animations and transitions are kept lightweight for performance.

---

## 2. Fact-Finding & User Interviews

We polled real users—students, young adults, and even parents—about their online shopping pain points:

| Concern                         | Response Summary                                    |
|----------------------------------|----------------------------------------------------|
| Confusing navigation             | Users want clear, visible categories               |
| Slow product search              | Need instant/product live search                   |
| Cart errors, lost items          | Must persist cart reliably and show analytics      |
| Flat design, boring visuals      | Responsive, lively sections and banners            |
| Frustrating authentication       | One-tab login/signup, simple password reset        |
| Hidden policies (refund, terms)  | Policies accessible from navigation/footers        |

**User Insights Used in Design:**
- Every main menu includes visible links with category, cart, wishlist, and FAQ.
- A persistent cart and wishlist indicator on all relevant pages.
- Live feedback with popups and highlights for cart/wishlist and errors.
- Distinct visual banners and color themes by section for fun and clarity.
- All legal and support info one click away.

---

## 3. Requirement Analysis

**User Stories:**
- **Shopper:** Browse categories (Men, Women, Kids, Accessories, Shoes) fast and easily.
- **User:** Save favorites to wishlist, edit cart from any device—no account/email required.
- **Admin/Contributor:** Update site policies, legal docs, and FAQ without touching JS code.
- **Guest:** Place orders, send feedback, see status—all without forced login.
- **Contributor:** Get automatic profile, stats, and team recognition via `contributors.html`.

**Technical Needs:**
- 100% static: deploy anywhere, no dependencies, works offline once loaded.
- Modular architecture: `/products/`, `/Style/`, `/script/` for feature separation.
- Modern CSS: Grid/flex layouts, responsive design.
- Vanilla JS (ES6+), no frameworks but code style allows future migration if needed.
- Local assets: Fast initial load, no CORS/dependency issues.
- Simple, clear code comments and `README.md` for future devs.

**Typical Data Flows:**
- Cart/wishlist stored in localStorage (`window.localStorage`), key is per-user/device, no backend sync.
- Product lists encoded in HTML; search scripted for client-side filtering.
- Contributor stats (in contributors.js) updated live by page logic.

---

## 4. Planning & Methodology

**Immediate Priorities:**
- One `index.html` for landing and promo, with always-on, responsive menu.
- Dedicated HTML pages for every category/feature/policy.
- Cart, wishlist, and FAQ as always-accessible features (not hidden in submenus).
- Popups (modals and notifications) to explain or confirm all key actions.

**Stack:**
- HTML5 for page markup.
- CSS3—split into `/Style/` per-category and root styles for site-wide look.
- JavaScript ES6+, one file per feature in `/script/`. Heavy functions are self-contained for easy removal or upgrade.
- Local font files (Futura family, see `/fonts/futura/` section).
- All images, icons, and logos in `/images`.

**Timeline Example:**
- Week 1 – Wireframe in Figma, implement index + navigation, basic CSS.
- Week 2 – Product HTML/CSS, add client-side cart/wishlist with localStorage.
- Week 3 – Integrate modals, policies, contributors, polish and responsiveness.

**Development Methodology:**
- Git-based agile: features split by directory or PR.
- Each new component (JS, CSS, HTML section) gets a single "owner" for review.
- PR template ensures description, test/UX checklist, and planned reviewer.
- JS files require minimum one distantly-related reviewer (e.g., UI for backend features).

---

## 5. Design & Diagrams

### 5.1 Project Structure (Logical Overview)
```plaintext
. (project root)
├── accessories.html
├── active.js
├── ai5.html
├── arrow_upper.png
├── Boy.html
├── cart.html
├── child.html
├── contact.html
├── contributors.css
├── contributors.html
├── contributors.js
├── day-mode.png
├── deepseek r1
│   ├── E4h4qW24My6G.com
│   │   ├── _next
│   │   │   └── static
│   │   │       ├── chunks
│   │   │       ├── css
│   │   │       └── media
│   │   └── deepr1.html
│   └── vPc0p7it8kpe.click
│       └── js
│           └── avrtcaPPj5A7.js
├── doc.md
├── doc.pdf
├── faq.html
├── features.html
├── feedback.html
├── fonts
│   └── futura
│       ├── futur.ttf
│       ├── Futura Bold font.ttf
│       ├── Futura Bold Italic font.ttf
│       ├── Futura Book font.ttf
│       ├── Futura Book Italic font.ttf
│       ├── Futura Extra Black font.ttf
│       ├── Futura Heavy font.ttf
│       ├── Futura Heavy Italic font.ttf
│       ├── futura light bt.ttf
│       ├── Futura Light font.ttf
│       ├── Futura Light Italic font.ttf
│       ├── futura medium bt.ttf
│       ├── futura medium condensed bt.ttf
│       ├── Futura Medium Italic font.ttf
│       ├── Futura XBlk BT.ttf
│       ├── tt0205m_.ttf
│       ├── unicode.futurab.ttf
│       └── unicode.futurabb.ttf
├── images
│   ├── Ahmed-abo.jpg
│   ├── Ahmed-sab.jpeg
│   ├── Ahmed-samh.jpg
│   ├── bag1.jpg
│   ├── bag2.jpg
│   ├── bag3.jpg
│   ├── bag4.jpg
│   ├── bag5.jpg
│   ├── bag6.jpg
│   ├── bag7.jpg
│   ├── bag8.jpg
│   ├── bag9.jpg
│   ├── bazufrill.webp
│   ├── Black Denim Joggers.webp
│   ├── Black Formal Shoes.webp
│   ├── blackstrippedmaneffectimage.jpg
│   ├── blackstrippedmannormal.jpeg
│   ├── booties.webp
│   ├── Bottom Wear.jpeg
│   ├── boy printed tshirt.jpg
│   ├── Boy Sneakers.jpeg
│   ├── Boys Loafer.webp
│   ├── boys round neck tshirt.webp
│   ├── butterfly.jpg
│   ├── Casual Camouflage Jogger.jpeg
│   ├── Casual Shoes.jpg
│   ├── category1.webp
│   ├── category2.webp
│   ├── category3.webp
│   ├── check shirt.webp
│   ├── childbanner.jpg
│   ├── chinatrade.avif
│   ├── cloth1.jpeg
│   ├── cloth10.jpeg
│   ├── cloth11.jpeg
│   ├── cloth12.jpeg
│   ├── cloth13.jpeg
│   ├── cloth14.jpeg
│   ├── cloth15.jpeg
│   ├── cloth16.jpeg
│   ├── cloth17.jpeg
│   ├── cloth18.jpeg
│   ├── cloth19.jpeg
│   ├── cloth2.jpeg
│   ├── cloth20.jpeg
│   ├── cloth3.jpeg
│   ├── cloth4.jpeg
│   ├── cloth5.jpeg
│   ├── cloth6.jpeg
│   ├── cloth7.jpeg
│   ├── cloth8.jpeg
│   ├── cloth9.jpeg
│   ├── clothingEthnic.webp
│   ├── confirmation.png
│   ├── cotton partywearkid2.webp
│   ├── coupleImage.png
│   ├── coupleimageForMainPage.jpeg
│   ├── customer1.jpg
│   ├── customer2.jpg
│   ├── customer3.jpg
│   ├── Elastic Waist Jeans.jpg
│   ├── embroided straigh kurta.webp
│   ├── fancy boy slipper.avif
│   ├── floralpattern.jpeg
│   ├── frill.jpg
│   ├── full sleeve shirt.webp
│   ├── girl banner.jpg
│   ├── girl leather.jpg
│   ├── girl sandals.jpg
│   ├── girl shoes.webp
│   ├── girls track pants.jpg
│   ├── green colour jacquard silk kurta.jpeg
│   ├── h1-slide-show-1_1_1.webp
│   ├── h1-slide-show-2.webp
│   ├── h1-slide-show-3.webp
│   ├── high heels.jpeg
│   ├── img1.jpg
│   ├── img10.jpg
│   ├── img11.jpg
│   ├── img12.jpg
│   ├── img13.jpg
│   ├── img14.jpg
│   ├── img15.jpg
│   ├── img16.jpg
│   ├── img17.jpg
│   ├── img18.jpg
│   ├── img19.jpg
│   ├── img2.jpg
│   ├── img20.jpg
│   ├── img3.jpg
│   ├── img4.jpg
│   ├── img5.jpg
│   ├── img6.jpg
│   ├── img7.jpg
│   ├── img8.jpg
│   ├── img9.jpg
│   ├── insta1.webp
│   ├── insta2.webp
│   ├── insta3.webp
│   ├── insta4.webp
│   ├── insta5.webp
│   ├── insta6.webp
│   ├── kids-girl-tops1.jpg
│   ├── kids-girls-baby-western-top-for-women-full.jpg
│   ├── kidsplazzo.webp
│   ├── kurta set.jpg
│   ├── Leather Shoes.jpg
│   ├── Legasy.jpg
│   ├── light up toddler       girl.webp
│   ├── Light Weight boys slippers.webp
│   ├── logo.png
│   ├── logo1.png
│   ├── Mainpagebanner.jpg
│   ├── Me.png
│   ├── Net Sequins Embroidered.jpg
│   ├── Pamper pants.jpeg
│   ├── pocket Mild Wash Bermuda Shorts.jpg_2000Wx3000H
│   ├── pocketSolidShorts.webp
│   ├── popup1.jpg
│   ├── printedlegging.webp
│   ├── printedpuffsleeves.webp
│   ├── product1-effect.jpg
│   ├── product1.webp
│   ├── product2-effect.jpg
│   ├── product2.jpg
│   ├── product3-effect.jpg
│   ├── product3.webp
│   ├── product4-effect.jpg
│   ├── product4.jpg
│   ├── product5-effect.jpg
│   ├── product5.jpg
│   ├── product6-effect.jpg
│   ├── product6.jpg
│   ├── product7-effect.jpg
│   ├── product7.jpg
│   ├── product8-effect.jpg
│   ├── product8.jpg
│   ├── pumps shoes.jpg
│   ├── rio girls tie and dye shirt.webp
│   ├── SALEACC.png
│   ├── sandal1.jpg
│   ├── sandal2.jpg
│   ├── sandal3.jpg
│   ├── sandal4.jpg
│   ├── sandal5.jpg
│   ├── sandal6.jpg
│   ├── sandal7.jpg
│   ├── sandal8.jpg
│   ├── shop-bags.webp
│   ├── shop-clothing.webp
│   ├── shop-glasses.webp
│   ├── shop-sandals.webp
│   ├── shop-sneakers.webp
│   ├── shortboys.png
│   ├── shorts.jpg
│   ├── sifli sikvans boy kurta.webp
│   ├── Stylish Shoes.jpg
│   ├── sunglasses1.jpg
│   ├── sunglasses2.jpg
│   ├── sunglasses3.jpg
│   ├── sunglasses4.jpg
│   ├── sunglasses5.jpg
│   ├── sunglasses6.jpg
│   ├── sunglasses7.jpg
│   ├── sunglasses8.jpg
│   ├── tealimageshirtmen.jpeg
│   ├── tealshirtmeneffect.jpeg
│   ├── toddler girl sandals.jpg
│   ├── Trendy Bottoms.jpg
│   ├── Trouser for Boys.webp
│   ├── twg.jpeg
│   ├── whitetshirtmen.jpeg
│   ├── whitetshirtmeneffect.jpeg
│   └── youngcouple1.jpg
├── index.html
├── login-sginup.html
├── mens.html
├── moon.png
├── ordertt.html
├── preloader.js
├── preloaderStyle.css
├── privacy.html
├── products
│   ├── bags.html
│   ├── productscss.css
│   ├── sandals.html
│   └── sunglasses.html
├── README.md
├── return-policy.html
├── script
│   ├── modal_box.js
│   ├── popup.js
│   ├── progressbar.js
│   └── share-button.js
├── shopclothing.html
├── sneaker.html
├── Style
│   ├── bags.css
│   ├── popup.css
│   ├── sandals.css
│   ├── sneaker.css
│   └── sunglasses.css
├── style.css
├── styles.css
├── terms-conditions.html
├── todo.html
├── wishlist.html
└── womens.html
```

- For each `.html`, there is optionally a matching `.css` in `/Style/` and JS handler in `/script/`.

### 5.2 Key UX/UI Relationships

```mermaid
flowchart TD
    index.html --> style.css
    index.html --> preloaderStyle.css
    index.html --> Style/popup.css
    cart.html & wishlist.html --> script/*
    all_pages --> preloader.js
    all_main_pages --> active.js
    contributors.html --> contributors.css
    contributors.html --> images/Me.png
    products/* --> Style/*
```

### 5.3 UI/UX Principles

- **Consistency:** Menus, buttons, color-schemes, and banners are consistent per category and through the whole site.
- **Mobile First:** All layouts start with mobile, progressive enhancement for desktop/tablet.
- **Accessibility:** Color contrast checks, keyboard support in all modals and navigation, image `alt` fields on all visuals.

---

## 6. Implementation

- **Navigation:** Dropdowns, hamburger menus, and active-tab highlight (via `active.js`). Keyboard and screen-reader accessible. Mobile menu overlays supported.
- **Product/Category Pages:** Gridded cards, lazy-loaded product images, price highlights, and “add/wishlist” buttons. Details/cards have hover states and accessible focus outlines.
- **Cart/Wishlist/Auth:** All cart/wishlist actions immediately persist to localStorage. Modals inform user of adds/removals/errors. Unified login-signup modal in `login-sginup.html`.
- **Popups/Modals:** Reusable modal logic (`modal_box.js`). Popups fired for cart actions, critical errors, or marketing (optional; heavy popups discouraged for UX).
- **Feedback/Contact:** Each form has client-side required-checks, instant error prompts, and clear success/error messages. Non-blocking rating stars/bar for feedback.
- **Search/FAQ:** Full instant (JS) filtering on product name/category. FAQ uses JS accordion, accessible and screen-reader friendly.
- **Contributors Page:** Loads team stats/bios dynamically, showing individual contributions, avatars, and dynamic badges for top contributors (updates via `contributors.js`).

**Modularization Philosophy:**
- All features are in their own files. To upgrade a feature, edit only that file/folder, rebuild only what’s needed.
- Every HTML/CSS/JS file follows a naming pattern for clarity.
- Comments explain all nontrivial JS and CSS logic.

**Example: Adding 'Back to Top' button:**
- Place its HTML snippet in `/includes/` or directly in common HTMLs.
- Link new `backtotop.js` in `/script/`, add styling in `/Style/backtotop.css`.
- Import and initialize in `index.html`, test on mobile/desktop.

---

## 7. Testing, Deployment & Maintenance

- **Browser coverage:** Chrome, Firefox, Edge, tested for rendering and event behavior. Safari checked for font/images.
- **Manual cross-device:** iOS and Android (emulators, device), check touch/scroll/hover and overlays.
- **Accessibility:** All key paths tested with keyboard, tab orders verified, all forms accessible via screen reader.
- **Performance:** All images optimized for fast load, CSS/JS split so each page loads only what it strictly needs.
- **Maintenance-friendly:** Every script/CSS modular and documented in-header. Policy pages and contributors use simple text, ready for non-engineers.
- **Backup/Restore:** Full site can be zipped and restored just by dragging to server/GitHub Pages.



## 8. Comprehensive Project Files & Folders Guide

### Root Directory

| File/Folder        | Type        | Info & Description                                                                                       |
|--------------------|-------------|---------------------------------------------------------------------------------------------------------|
| accessories.html   | HTML        | Accessories section page listing all accessory products.                                                 |
| active.js          | JS          | Handles main navigation, active tab highlights.                                                         |
| ai5.html           | HTML        | Experimental/testing workspace; not for production (sandbox code/UI).                                   |
| arrow_upper.png    | Image       | UI icon for "back to top" or scroll-to-section controls.                                                |
| Boy.html           | HTML        | Landing/category page for boy's fashion.                                                                |
| cart.html          | HTML        | Interface for viewing, editing, and checking out the shopping cart; tied to cart/wishlist logic.        |
| child.html         | HTML        | Child-wear landing page, special offers and promotions for kids.                                        |
| contact.html       | HTML        | Contact and inquiry form page; for user messages.                                                       |
| contributors.css   | CSS         | Styling for contributors.html, incl. avatars & badges.                                                  |
| contributors.html  | HTML        | Team/contributors showcase; dynamically updated with bios, stats, badges.                               |
| contributors.js    | JS          | Runs/statistics logic for contributors.html, like profile management and "top contributor" badges.       |
| day-mode.png       | Image       | Day/light mode toggle icon (theme switching).                                                           |
| deepseek r1/       | Directory   | Legacy/experimental/3rd-party or research code/assets. **Not part of active user-facing site!**         |
| doc.md             | Markdown    | This full user & dev documentation ("master reference" document).                                       |
| doc.pdf            | PDF         | PDF export/printout of documentation.                                                                   |
| faq.html           | HTML        | Frequently Asked Questions section, has expandable answers.                                             |
| features.html      | HTML        | Showcase for detailed features and screenshots of modules.                                              |
| feedback.html      | HTML        | Feedback form page; includes rating system & comment box.                                               |
| fonts/             | Directory   | Houses auxiliary font files (see below for detailed breakdown).                                         |
| images/            | Directory   | All static images (products, avatars, icons, banners, logos, etc); see section below.                   |
| index.html         | HTML        | Site homepage/landing page; main navigation, banners, promos, search.                                   |
| login-sginup.html  | HTML        | Unified modal-based login and signup page; no external authentication required.                         |
| mens.html          | HTML        | Men's clothing and accessories landing page/featured styles.                                            |
| moon.png           | Image       | Dark/night mode toggle icon (theme switching).                                                          |
| ordertt.html       | HTML        | Order summary/sample order tracker; for viewing placed orders.                                          |
| preloader.js       | JS          | Logic for loading animations and handling page transitions.                                             |
| preloaderStyle.css | CSS         | Styles for animated preloader/display during loading.                                                   |
| privacy.html       | HTML        | Legal privacy policy (GDPR-compliant).                                                                  |
| products/          | Directory   | All main product category pages (HTML), plus shared product styles.                                     |
| README.md          | Markdown    | Quick start and setup reference (short form for new devs).                                              |
| return-policy.html | HTML        | Returns and refunds policy (customer rights and steps).                                                 |
| script/            | Directory   | All modular site JS for UI/feature logic (see below for detailed).                                      |
| shopclothing.html  | HTML        | Main gallery page for all clothing items; mixes categories.                                             |
| sneaker.html       | HTML        | Sneaker product page, includes all styles with dynamic offers.                                          |
| Style/             | Directory   | Modular CSS by category/feature; custom theme vars and section styles.                                  |
| style.css          | CSS         | Main global CSS: base, resets, shared typography and variables.                                         |
| styles.css         | CSS         | Additional global overrides, typically for root/landing tweaks.                                         |
| terms-conditions.html| HTML      | Terms of service, usage policies, customer/legal obligations.                                           |
| todo.html          | HTML        | Team/project TODO page; current active/planned tasks (project management).                              |
| wishlist.html      | HTML        | Wishlist view; displays all favorited products, works client-side.                                      |
| womens.html        | HTML        | Women's collection: clothing, top offers, featured styles, etc.                                         |

---

### /products/

| File               | Type        | Info & Description                                                                |
|--------------------|-------------|----------------------------------------------------------------------------------|
| bags.html          | HTML        | Dedicated page for shopping/selecting bags; special offers, banners.              |
| sandals.html       | HTML        | Sandal category page; seasonal sub-sections, multi-product listing.               |
| sunglasses.html    | HTML        | Sunglasses/shades product page; discounts and banners.                            |
| productscss.css    | CSS         | Shared styling sheet for all product HTMLs in this directory.                     |

---

### /fonts/futura/

| File                        | Type        | Info & Description                                   |
|-----------------------------|-------------|------------------------------------------------------|
| futur.ttf                   | Font (TTF)  | Futura Regular TrueType font.                        |
| Futura Bold font.ttf        | Font (TTF)  | Futura Bold weight.                                  |
| Futura Bold Italic font.ttf | Font (TTF)  | Futura Bold Italic weight.                           |
| Futura Book font.ttf        | Font (TTF)  | Book/medium-light version of Futura.                 |
| Futura Book Italic font.ttf | Font (TTF)  | Italicized Book font.                                |
| Futura Extra Black font.ttf | Font (TTF)  | Extra Black (ultra-bold) Futura.                     |
| Futura Heavy font.ttf       | Font (TTF)  | Heavy/boldest variation.                             |
| Futura Heavy Italic font.ttf| Font (TTF)  | Heavy weight in Italic style.                        |
| futura light bt.ttf         | Font (TTF)  | Light/very thin Futura.                              |
| Futura Light font.ttf       | Font (TTF)  | Light.                                               |
| Futura Light Italic font.ttf| Font (TTF)  | Light Italic.                                        |
| futura medium bt.ttf        | Font (TTF)  | Medium.                                              |
| futura medium condensed bt.ttf| Font (TTF)| Condensed Medium Futura.                             |
| Futura Medium Italic font.ttf| Font (TTF) | Medium Italic.                                       |
| Futura XBlk BT.ttf          | Font (TTF)  | Extra Black (Special).                               |
| tt0205m_.ttf                | Font (TTF)  | Miscellaneous Futura variant.                        |
| unicode.futurab.ttf         | Font (TTF)  | Unicode Futura (black weight).                       |
| unicode.futurabb.ttf        | Font (TTF)  | Unicode Futura (bold/black).                         |

---

### /images/

| File (sample)            | Type   | Info & Description                              |
|--------------------------|--------|-------------------------------------------------|
| Ahmed-abo.jpg            | Image  | Contributor avatar.                             |
| bag1.jpg, bag2.jpg...    | Image  | Product photos for bags.                        |
| Black Denim Joggers.webp | Image  | Product photo, apparel.                         |
| logo.png, logo1.png      | Image  | Site main logo (used in headers/footers).       |
| Me.png                   | Image  | Contributor avatar (for contributors.html).      |
| day-mode.png, moon.png   | Image  | Theme toggle icons (day/night).                 |
| ...                      | ...    | ... (Contains **all** product shots, avatars, banners, UI icons, and more.) |

*Images are grouped by role: contributor avatars, product assets, UI elements, seasonal banners, icons, and logos. All are referenced in HTML, CSS, and used for styling/content.*

---

### /script/

| File            | Type | Info & Description                                                                  |
|-----------------|------|-------------------------------------------------------------------------------------|
| modal_box.js    | JS   | Handles all modal, popup, content open/close, and accessibility logic.              |
| popup.js        | JS   | Lightweight toast/notification logic for user alerts, info overlays.                |
| progressbar.js  | JS   | Displays and animates progress bars (e.g., checkout steps, cart progress visualized).|
| share-button.js | JS   | Provides "share this" functionality across products and site, clipboard integration. |

---

### /Style/

| File           | Type | Info & Description                                                                     |
|----------------|------|----------------------------------------------------------------------------------------|
| bags.css       | CSS  | Styles for bags.html (bags product page only).                                         |
| popup.css      | CSS  | Universal popup/modal styling (used across site for feedback, notifications, etc.).   |
| sandals.css    | CSS  | Styles for sandals.html category page.                                                 |
| sneaker.css    | CSS  | Styles for sneaker.html product section.                                               |
| sunglasses.css | CSS  | Styles for sunglasses.html product section.                                            |

*All style files follow component/category scope; use CSS custom properties for themes.*

---

### /deepseek r1/

| File/Folder                                    | Type       | Info & Description                                       |
|------------------------------------------------|------------|----------------------------------------------------------|
| E4h4qW24My6G.com/_next/static/                 | Directory  | Legacy/experimental static assets from 3rd-party demo.   |
| vPc0p7it8kpe.click/js/avrtcaPPj5A7.js          | JS         | Example/sample code from imported demo.                   |
| *deepr1.html*                                  | HTML       | Related legacy/demo HTML, not used on main site.         |

*The entire folder is considered archived/not part of the core/final project.*

---

> **Legend / Type Key:**  
> - _HTML_: Web page  
> - _CSS_: Stylesheet  
> - _JS_: JavaScript logic  
> - _Image_: Static image asset (JPG, PNG, WEBP, etc.)  
> - _Font_: Typography/font file  
> - _Markdown_: Documentation in Markdown format  
> - _PDF_: Portable Document Format  
> - _Directory_: Folder (may contain more of above)  

---

### Navigation Notes

- Each `.html` page may optionally have a matching .css file in `/Style/` and JS handler in `/script/`.
- All images, fonts, and scripts are referenced by relative path for portability.
- To add, swap, or remove a feature, update the corresponding file(s)/directory and modify this section.

---

## 9. Development Team & Technical Roles

**Technical Members:**
| Name             | Primary Focus by color                                   |
|------------------|----------------------------------------------------|
| Ali Ezz Ali      | perpol |
| Ahmed Abo Bakr   | red    |
| Ahmed Sabery     | green        |

**Non-Technical & UX:**
| Name              | Main Contributions                                |
|-------------------|---------------------------------------------------|
| Ahmed Sameh       | blue  |
| Abdrhamn Khaled   | yealow         |

- Reach via GitHub Issues or Notion (preferred), or on PR for code/content.

---

## 10. Feature Breakdown

- **Category Browsing:** Men, Women, Kids, Accessories, Shoes—core navigation, always present; grid/filters JS.
- **Cart & Wishlist:** LocalStorage state; clear, persistent; JS-based.
- **Authentication & Popups:** Modal-driven, simple validation; password reset, one-tab UX.
- **Product Search & FAQ:** Instantly filters products and FAQ answers client-side.
- **Theme Switcher:** Day/night toggle, persists preference.
- **Feedback/Forms:** Real-time validation, star/slider ratings.
- **Team/Contributors:** Live bios, avatars, and badge logic for active team.
- **Policy Pages:** Clear, accessible, no code experience needed for editors.

---

## 11. Deployment & Running

- No backend/build step! Works anywhere—Python server, Netlify, GitHub Pages.
- **Deployment example:** (see root for more)
```sh
python3 -m http.server 8080
# Open http://localhost:8080 or on network: http://192.168.x.x:8080
```
- For Netlify, just drag, for GitHub Pages push to main branch.
- Refresh browser cache for style/image updates.

---

## 12. Developer FAQ

- **How do I add a category/product?**
  1. Copy an existing HTML in `/products/` or root.
  2. Edit content, update links.
  3. Add to menu in `style.css` and relevant scripts.

- **Where do I add images/fonts?**
  - Put in `/images` or `/fonts/futura/`, reference by relative path in HTML/CSS.
- **How do I create a new JS or CSS feature?**
  - Place file in `/script/` or `/Style/`, link in relevant HTML, comment at top with feature/purpose.
- **How do I get code reviewed?**
  - Push to PR and request peer/team review; see `/contributors.html` for current team.
- **Want to join team?**
  - See `/contributors.html`, add entry, and avatar, update logic in `/contributors.js`.

---

## 13. Code Quality, Security & Accessibility

- **Code:** Clear, modular, BEM CSS, ES6 JS only, explained in comments.
- **Security:** All local-only, never submits/stores sensitive data, avoids 3rd-party scripts.
- **Accessibility:** Follows WAI-ARIA, alt tags on images/assets, tabbing and contrast checked.

---

## 14. Contribution Guidelines

- Modularize everything—one feature per file/folder when possible.
- Test UI in Chrome, Firefox, and mobile on every PR.
- All major changes must update this `doc.md`.
- Review PRs for style, intent, security, and UX.
- Keep images/compressed, code commented, contributors page up-to-date.

---

*End of 5*A E-commerce Project Unified Documentation*
