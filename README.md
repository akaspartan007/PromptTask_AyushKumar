# 🖥️ Smart E-Commerce IT Product Discovery & Quote Management System

🔗 **Live Demo:** [goldenresponsetraining.netlify.app](https://goldenresponsetraining.netlify.app)

A production-grade, fully static storefront for discovering, comparing, and requesting quotes on professional IT products — teleprompters, laptops, and accessories. Zero server runtime required.

---

## 📁 Project Structure

```
├── index.html
├── teleprompters.html
├── laptop_categories.html
├── it-products.html
├── product.html
├── compare.html
├── contact.html
├── navbarhtml.txt
├── data/
│   └── products.json
└── js/
    ├── script.js
    ├── search.js
    ├── ai-product-finder.js
    ├── chatbot.js
    ├── comparison.js
    ├── quote-modal.js
    ├── index-products.js
    ├── teleprompters.js
    ├── laptop_categories.js
    ├── it-products.js
    └── product.js
```

---

## ✨ Features

- **Rule-Based AI Product Finder** — Natural language input parsed via token matching, price ceiling extraction, and relevance scoring to surface best-fit products
- **Live Autocomplete Search** — Real-time catalog search across name, brand, specs, and category with debounced dropdown suggestions
- **Product Catalog Pages** — Dedicated, filterable catalog views for Teleprompters, Laptops, and IT Accessories
- **Product Deep-Dive Pages** — Full spec sheets with feature badges, ratings, and pricing per product
- **Side-by-Side Comparison Matrix** — Compare up to 3 products with a full spec table, feature highlights, and quote triggers
- **B2B Quote Modal** — Validated quote request form with quantity, urgency, and notes fields; calculates MSRP baseline estimate
- **Floating Chatbot Assistant** — Tree-structured navigation bot for instant product discovery guidance
- **Persistent Compare State** — localStorage sync keeps the comparison list intact across all pages
- **Fully Responsive Design** — Mobile drawer navigation, adaptive grids, and touch-friendly controls throughout

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | Tailwind CSS (CDN) |
| Icons | Feather Icons |
| Fonts | Google Fonts — Inter, Poppins |
| Logic | Vanilla JavaScript (ES6+ Modules) |
| Data | Static JSON (`data/products.json`) |
| State | localStorage |

No build tools, bundlers, or server runtimes required.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/it-showroom.git
cd it-showroom
```

### 2. Serve locally

Since the app fetches `data/products.json` via `fetch()`, you need a local server (opening `index.html` directly in a browser will cause CORS errors).

**Option A — VS Code Live Server**
Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) and click **Go Live**.

**Option B — Python**
```bash
python -m http.server 8080
```

**Option C — Node.js**
```bash
npx serve .
```

Then open `http://localhost:8080` in your browser.

---

## 📄 Pages

| Page | File | Description |
|---|---|---|
| Home / Dashboard | `index.html` | Hero section, AI finder, category cards, product grid |
| Teleprompters | `teleprompters.html` | Filterable catalog — Studio, Broadcast, Portable |
| Laptops | `laptop_categories.html` | Filterable catalog — Business Elite, Consumer |
| IT Accessories | `it-products.html` | Filterable catalog — Mice, Keyboards, Hubs |
| Product Detail | `product.html?id=<id>` | Full spec sheet for a single product |
| Compare | `compare.html` | Side-by-side spec matrix (max 3 products) |
| Contact | `contact.html` | Corporate inquiry form + HQ info |

---

## ⚙️ JavaScript Modules

| File | Role |
|---|---|
| `script.js` | Core orchestrator — navbar injection, mobile drawer, shared product card builder, JSON data fetcher |
| `search.js` | Live autocomplete search engine with debounce |
| `ai-product-finder.js` | Rule-based intent parser — category detection, price ceiling extraction, keyword scoring |
| `chatbot.js` | Floating assistant bot with tree-structured dialog nodes |
| `comparison.js` | localStorage comparison state sync, badge updates, compare table renderer |
| `quote-modal.js` | Quote modal — product snapshot, form validation, MSRP estimate |
| `index-products.js` | Homepage product grid with category filter buttons |
| `teleprompters.js` | Teleprompter catalog renderer with subcategory filters |
| `laptop_categories.js` | Laptop catalog renderer with subcategory filters |
| `it-products.js` | Accessories catalog renderer with subcategory filters |
| `product.js` | Single product deep-dive page renderer, URL param parsing |

---

## 🗃️ Data

All product data lives in `data/products.json`. Each product entry includes:

```json
{
  "id": "unique-id",
  "category": "teleprompter | laptop | accessory",
  "subcategory": "studio | broadcast | portable | business | consumer | mouse | keyboard | hub",
  "title": "Product Name",
  "brand": "Brand Name",
  "price": 999.00,
  "rating": 4.8,
  "reviewsCount": 42,
  "image": "https://...",
  "summary": "Short description",
  "description": "Full description",
  "specs": { "Key": "Value" },
  "features": ["Feature 1", "Feature 2"]
}
```

To add new products, append entries to `data/products.json` following the schema above.

---

## 🔍 AI Product Finder — How It Works

The finder uses client-side rule matching — no external API required:

1. **Category Detection** — Keyword scan for terms like `teleprompter`, `laptop`, `mouse`, `keyboard`
2. **Price Ceiling Extraction** — Regex matches phrases like `under $500`, `max 1000`, `budget of 300`
3. **Feature Keywords** — Tokens like `portable`, `business`, `wireless`, `mechanical` boost relevant products
4. **Scoring & Ranking** — Each product receives a weighted score; results are sorted descending and rendered as cards

---

## 📊 Comparison Engine

- Add any product to the compare list via the **columns icon** on product cards or the detail page
- Maximum **3 products** can be compared simultaneously
- State persists in `localStorage` across page navigation
- The compare badge in the navbar updates live on all pages
- The `compare.html` page renders a full spec-row table with a quote button per column

---

## 📬 Quote Modal

Triggered from any product card or detail page. The form collects:

- Contact name (min 2 characters)
- Corporate email (regex validated)
- Quantity (1–500 units)
- Urgency schedule (Standard / Expedited / Immediate)
- Optional configuration notes

On valid submission, an MSRP baseline estimate is calculated (`price × quantity`) and an alert confirms the request.

---

## 🤖 Chatbot Assistant

The floating chat widget uses a pre-defined conversation tree (`conversationNodeTree`) to guide users:

- Teleprompter Systems → catalog page
- Laptop Catalogues → catalog page  
- Request Quote Process → contact page

No external API is used. All responses are local.

---

## 🚢 Deployment

This is a fully static site — deploy to any static host:

- **GitHub Pages** — push to a `gh-pages` branch or enable Pages on `main`
- **Netlify** — drag and drop the project folder
- **Vercel** — `vercel --prod` from the project root
- **AWS S3 + CloudFront** — upload files and configure static website hosting

No environment variables or build steps needed.

---
