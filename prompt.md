# ARS Solutions India: Smart IT Product Discovery & Quote Management System

## Context and Role

You are a **Frontend Web Developer** specializing in **e-commerce web application development** and are required to design and develop an intelligent and feature-rich IT Product Showcase & E-Commerce Platform titled:

**ARS Solutions India: Smart IT Product Discovery & Quote Management System**

The platform must provide a smooth, responsive, and visually engaging experience that allows users to:

- Browse IT products
- Compare products
- Search intelligently
- Request quotations
- Discover suitable products using AI-assisted filtering

The application should support both **B2B and B2C users** and operate as a modern frontend-only web application.

---

# Objective

Develop a complete frontend IT product showcase system that:

- Displays IT products across multiple categories
- Supports AI-powered search and filtering
- Enables side-by-side product comparison
- Provides quote and inquiry functionality
- Ensures responsive and interactive UI
- Simplifies buyer decision-making

The system must deliver a **fast, modern, and accessible experience**.

---

# Core System Requirements

## Product Showcase and Discovery

Develop an all-in-one IT showcase where users can:

- Browse products across categories
- View detailed product pages
- Filter and sort products
- Use AI-assisted product finder
- Compare products
- Submit quote requests

All product rendering must use **JSON-driven frontend logic**.

---

# Product Categories

The platform must support:

## 1. Teleprompters
- Studio teleprompters
- Broadcast teleprompters
- Portable teleprompters

## 2. Laptops
- Business laptops
- Consumer laptops

## 3. IT Products and Accessories
- Mouse
- Keyboard
- USB hubs
- Peripheral devices

---

# Product Listing Requirements

Users must be able to:

- Browse category pages
- View product details
- See specifications and pricing
- View product images
- Add products to comparison
- Submit quote requests

All product data must be loaded dynamically from:

```text
data/products.json
```

---

# AI Product Finder Requirements

Implement a **rule-based NLP Product Finder**.

The system must:

- Accept natural language input
- Detect category keywords
- Detect price range
- Detect brand or feature preferences
- Return ranked recommendations
- Display suggestions in a clean UI

Examples:

```text
Laptop under $700
Wireless mouse for office use
Broadcast teleprompter
```

No external AI APIs are allowed.

---

# Product Comparison Requirements

Provide side-by-side comparison.

Users must be able to:

- Add up to 3 products
- Compare specs and prices
- Remove products
- Clear comparison list
- View best-value indicators

Comparison must dynamically update using JSON data.

---

# Quote and Contact Requirements

## Quote Modal

Users must be able to:

- Enter name
- Enter email
- Enter phone
- Enter requirements
- Submit inquiry

Frontend validation is required.

After submission:

- Show confirmation message

---

## Contact Page

Must include:

- Company information
- Contact form
- Social links
- Optional Google Maps embed

---

# Search Requirements

Implement live search that:

- Searches product names
- Searches descriptions
- Filters results instantly
- Displays dropdown suggestions
- Navigates to product pages

Search must work globally via shared navbar.

---

# Chatbot Requirements

Implement a rule-based chatbot widget.

The chatbot must:

- Float across pages
- Accept product queries
- Return predefined responses
- Guide users to pages
- Include open/close animations

No backend chatbot API allowed.

---

# Frontend Requirements

The frontend must use:

- HTML5
- CSS3
- Tailwind CSS CDN
- Vanilla JavaScript ES6+

UI must be:

- Responsive
- Accessible
- Fast-loading
- Modern

Heavy frameworks are not allowed.

---

# Required Pages

The application must include:

| Page | Purpose |
|---|---|
| index.html | Homepage |
| teleprompters.html | Teleprompter listings |
| laptop_categories.html | Laptop listings |
| it-products.html | Accessories |
| product.html | Product details |
| compare.html | Comparison |
| contact.html | Contact |
| quote-modal.html | Reusable quote modal |

---

# Shared Components

Maintain:

```text
navbarhtml.txt
components/css/style.css
components/css/product.css
components/css/compare.css
```

---

# JavaScript Module Requirements

Develop:

```text
script.js
search.js
ai-product-finder.js
chatbot.js
comparison.js
index-products.js
teleprompters.js
laptop_categories.js
it-products.js
product.js
```

All JS must use:

```javascript
fetch()
```

to load data from:

```text
data/products.json
```

---

# Data Requirements

Use a single JSON database.

Each product must include:

```json
{
"id":"",
"name":"",
"category":"",
"price":"",
"image":"",
"description":"",
"specs":{},
"brand":"",
"rating":"",
"badge":""
}
```

This JSON file is the **single source of truth**.

---

# Design and Branding

## Brand Identity

**Brand:** ARS Solutions India

**Logo:**  
images/ARSSolutionsLogo.png

### Colors

- Primary: #0ea5e9
- Secondary: #64748b
- Dark: #0f172a

### Fonts

- Body: Inter
- Heading: Poppins

---

# Required UI Components

Include:

- Fixed navbar
- Mega menu
- Mobile menu
- Hero section
- Category cards
- Product cards
- Product detail layout
- Comparison UI
- Quote modal
- Chatbot
- Footer

---

# Technology Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 + Tailwind |
| Logic | Vanilla JS |
| Icons | Feather Icons |
| Fonts | Google Fonts |
| Data | JSON |
| Version Control | Git + GitHub |
| Deployment | GitHub Pages |

---

# Explicit Constraints

The solution must satisfy all of the following:

1. Use **HTML5, Tailwind CSS, and Vanilla JavaScript only**.
2. All product data must come from **data/products.json**.
3. Product comparison must support **maximum 3 products**.
4. No backend or external APIs may be used.
5. Deployment must work on **GitHub Pages using relative paths**.

---

# Testing Requirements

Perform:

- Chrome testing
- Firefox testing
- Responsive testing
- Form validation testing
- Console validation
- Cross-browser testing

---

# Deployment Requirements

Deploy using:

- GitHub Pages
- Main branch
- Relative URLs only

Expected format:

```text
https://username.github.io
```

No build tools or bundlers allowed.

---

# Output Requirements

The final solution must provide:

- Multi-page website
- AI-assisted finder
- Product comparison
- Quote modal
- Live search
- Chatbot
- Responsive UI
- JSON rendering
- Clean modular JavaScript
- Production-ready deployment
