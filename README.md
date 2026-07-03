# Industrial Fans India — Website

**Complete corporate website for Industrial Fans India Private Limited**  
Built from the three product catalogues provided. ISO 9001:2008 certified manufacturer of industrial fans, blowers and dampers, Chennai, India.

---

## 📁 Folder Structure

```
indfans/
├── index.html                      ← Homepage
├── sitemap.xml                     ← XML sitemap (update domain after deploy)
├── robots.txt                      ← Search engine instructions
├── css/
│   └── style.css                   ← Complete stylesheet (all pages)
├── js/
│   └── main.js                     ← All JavaScript (header, forms, counters, scroll)
├── images/                         ← Place product images here (see below)
│   └── hero-bg.jpg                 ← Hero background photo (see below)
├── downloads/                      ← Place PDF catalogues here
│   ├── Damper_Brochure.pdf         ← Damper catalogue PDF
│   ├── FANS.pdf                    ← Centrifugal fan catalogue PDF
│   └── HIGH_PRESSURE_FANS.pdf      ← High pressure fan catalogue PDF
└── pages/
    ├── about.html                  ← About Us
    ├── products.html               ← Products overview
    ├── industries.html             ← Industries served
    ├── services.html               ← Engineering services
    ├── downloads.html              ← Downloads page
    ├── contact.html                ← Contact & inquiry form
    └── products/                   ← Individual product pages (13 pages)
        ├── centrifugal-fans.html
        ├── high-pressure-fans.html
        ├── series-fans.html
        ├── butterfly-dampers.html
        ├── multilouver-dampers.html
        ├── double-flap-dampers.html
        ├── biplane-dampers.html
        ├── guillotine-dampers.html
        ├── diverter-dampers.html
        ├── goggle-valves.html
        ├── emergency-dampers.html
        ├── coffee-pot-dampers.html
        └── stack-dampers.html
```

---

## 🚀 Deployment Instructions

### Option 1 — Shared Hosting (cPanel / FileZilla)
1. Zip the entire `indfans/` folder
2. Log into your cPanel → File Manager → `public_html/`
3. Upload and extract the zip
4. All files should be accessible at `https://www.indfans.net/`

### Option 2 — FTP Upload
1. Open FileZilla and connect to your hosting server
2. Navigate to `public_html/` on the server
3. Upload all files maintaining the folder structure
4. Ensure `index.html` is at the root of `public_html/`

### Option 3 — Netlify (Free, Recommended for Testing)
1. Go to [netlify.com](https://netlify.com) → "Add new site" → "Deploy manually"
2. Drag and drop the entire `indfans/` folder
3. Your site will be live at a `.netlify.app` URL within seconds
4. Add your custom domain `indfans.net` in site settings

### Option 4 — Vercel
1. `npm install -g vercel`
2. `cd indfans && vercel --prod`
3. Follow the prompts to deploy

---

## 📸 Images Required

All image placeholders are currently SVG icons on dark gradient backgrounds. Replace with real product photos for maximum impact.

### Hero Background (`/images/hero-bg.jpg`)
- Recommended: Wide industrial photo (factory floor, large fan, or industrial plant)
- Size: 1920×1080px minimum, compressed to <500KB
- The CSS already references this file in `.hero-bg`

### Product Images
Place product photos in `/images/products/` and update the `product-card-img` divs in product pages:
```html
<!-- Replace this: -->
<div class="placeholder">...</div>

<!-- With this: -->
<img src="../../images/products/centrifugal-fan-01.jpg" alt="Centrifugal Fan" loading="lazy">
```

Recommended photo names:
- `centrifugal-fan-01.jpg`, `centrifugal-fan-02.jpg`
- `high-pressure-blower-01.jpg`
- `series-fans-blast-furnace.jpg`
- `butterfly-damper-01.jpg`, `butterfly-damper-02.jpg`
- `guillotine-damper-01.jpg`
- `goggle-valve-01.jpg`
- `diverter-damper-01.jpg`
- etc.

### Recommended Photo Size
- Cards: 800×500px, <100KB each
- Hero images: 1200×600px, <200KB each
- Use WebP format for best performance

---

## 📄 PDF Catalogues Setup

Copy your three catalogue PDFs to the `/downloads/` folder:
```
/downloads/Damper_Brochure.pdf          ← Damper_Brochure_-_Approved.pdf
/downloads/FANS.pdf                     ← FANS-Approved.pdf
/downloads/HIGH_PRESSURE_FANS.pdf       ← HIGH_PRESSURE_FANS-Approved.pdf
```
The download links in `downloads.html` and product pages will work automatically.

---

## 📧 Contact Form Setup

The contact form currently shows a success message in the browser. To make it actually send emails, choose one of:

### Option A — Formspree (Easiest, Free)
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form and get your form ID (e.g. `xvgknpqr`)
3. In `pages/contact.html`, change the form action:
```html
<form action="https://formspree.io/f/xvgknpqr" method="POST">
```
4. Remove `novalidate` and the JavaScript form handler (keep only the validation)

### Option B — EmailJS (No Backend Needed)
1. Sign up at [emailjs.com](https://emailjs.com)
2. Add to `<head>`: `<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>`
3. Configure service and replace the form submit handler in `main.js`

### Option C — PHP (Shared Hosting)
Create `send-mail.php` in the root and point the form action to it:
```php
<?php
$to = "uday@indfans.com";
$subject = "Inquiry from " . $_POST['company'];
$message = "Name: {$_POST['name']}\nEmail: {$_POST['email']}\nPhone: {$_POST['phone']}\n\n{$_POST['message']}";
mail($to, $subject, $message);
header("Location: contact.html?sent=1");
?>
```

---

## 🔧 Customisation

### Update Company Details
Search and replace across all files:
- `+91 44 4282 2563` → your office number
- `+91 99401 83279` → your mobile number
- `uday@indfans.com` → your email
- `www.indfans.net` → your domain

### Update the WhatsApp number
In all pages, change:
```
https://wa.me/919940183279
```
to your WhatsApp number (international format, no + or spaces).

### Google Analytics
Add before `</head>` in all pages:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Update Domain in sitemap.xml
Replace `https://www.indfans.net` with your actual live domain in `sitemap.xml`.

### Google Search Console
1. Verify site ownership at [search.google.com/search-console](https://search.google.com/search-console)
2. Submit `sitemap.xml`
3. Request indexing of key pages

---

## ✅ Pre-Launch Checklist

- [ ] Upload all files to `public_html/`
- [ ] Place 3 PDF catalogues in `/downloads/`
- [ ] Add hero background image (`/images/hero-bg.jpg`)
- [ ] Add product photos to `/images/products/`
- [ ] Configure contact form email (Formspree recommended)
- [ ] Update WhatsApp number in all pages
- [ ] Update domain in `sitemap.xml`
- [ ] Add Google Analytics tracking code
- [ ] Submit sitemap to Google Search Console
- [ ] Test on mobile, tablet and desktop
- [ ] Test all navigation links
- [ ] Test contact form submission
- [ ] Test PDF downloads
- [ ] Check Google Maps embed displays correctly
- [ ] Test WhatsApp button opens correctly

---

## 📊 SEO Features Included

- ✅ Unique `<title>` and `<meta description>` on every page
- ✅ `<link rel="canonical">` tags
- ✅ Schema.org JSON-LD structured data (Organization, Product, ContactPage)
- ✅ XML Sitemap (`sitemap.xml`)
- ✅ `robots.txt`
- ✅ Semantic HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ✅ ARIA labels on interactive elements
- ✅ Alt text placeholders on all images
- ✅ `loading="lazy"` on images
- ✅ Open Graph meta tags on homepage
- ✅ Mobile-responsive (passes Google Mobile-Friendly test)
- ✅ Fast loading (no heavy frameworks)

---

## 🌐 Technology Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 (semantic) |
| Styling | Custom CSS (CSS Variables, Grid, Flexbox) |
| JavaScript | Vanilla ES6+ (no jQuery, no framework) |
| Icons | Font Awesome 6 (CDN) |
| Fonts | Google Fonts — Bebas Neue, Rajdhani, Inter |
| Maps | Google Maps Embed API |
| Forms | Client-side validation (connect to Formspree/EmailJS/PHP) |

---

## 📞 Support

For questions about this website code, contact the developer.  
For product enquiries: **uday@indfans.com** | **+91 99401 83279**

---

*Industrial Fans India Private Limited — An ISO 9001:2008 Company*  
*28, Aruna Apartment, 3A-3rd Floor, New Boag Road, T. Nagar, Chennai – 600017*
