VELORA GITHUB STORE
===================

Files:
- index.html       Main storefront
- products.json    Product catalog
- images/          Put your own local product images here if desired

INSTALL ON GITHUB PAGES
1. Open your GitHub repository.
2. Upload index.html and products.json to the repository root.
3. Commit the changes.
4. Keep both files in the SAME folder.
5. Open your GitHub Pages site.

IMPORTANT
- products.json is loaded automatically by index.html.
- When you edit products.json, commit the file to GitHub. GitHub Pages may take a short time to publish the change.
- The storefront adds a cache-busting query when loading products.json.
- External demo images currently use Unsplash URLs. Replace these image URLs with your own product image URLs or local paths such as images/product1.jpg.

GOOGLE APPS SCRIPT ORDER BACKEND
The HTML has:
  const CONFIG = {
    productsUrl: "products.json",
    orderApiUrl: "",
    orderLookupApiUrl: ""
  };

After your Apps Script web app is working, put its /exec URL into orderApiUrl.
Do NOT put your Telegram bot token, API keys, payment secrets, or private credentials in index.html.

ONLINE PAYMENT
The checkout UI includes COD and Online Payment selection, but a real payment gateway must be connected to the backend before accepting online payments. Do not treat the Online Payment option as a live payment processor yet.

PRODUCT JSON FORMAT
Each product supports:
id, name, category, subcategory, price, mrp, discount, description,
images[], sizes[], colors[], stock, rating, reviewCount, createdAt

PRODUCT UPDATE
To add a product, add another object to products.json following the existing structure.
To change price/stock/images, edit the corresponding fields and commit.

LOCAL TESTING
Use GitHub Pages or another HTTP server. Opening index.html directly with file:// can prevent fetch("products.json") from working in some browsers.

BACKEND SECURITY
Customer order data should be handled by your secure Apps Script/backend. Keep private Telegram credentials server-side only.
