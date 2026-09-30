# Amazon Project

An Amazon-inspired e-commerce web application built with vanilla JavaScript, CSS, and HTML. It provides a complete shopping experience with a product catalog, shopping cart, checkout page, order history, and package tracking—all running client-side with localStorage for cart persistence.

## 🛠️ Stack

- **Languages:** JavaScript (43.9%), CSS (31.6%), HTML (24.5%)
- **Runtime:** Vanilla JavaScript (ES6 modules)
- **Key Libraries:** [dayjs](https://day.js.org/) for date formatting and calculations

## 📁 Project Structure

```
amazon-project/
├── amazon.html                 # Product catalog page
├── checkout.html               # Shopping cart review & payment page
├── orders.html                 # Order history and status
├── tracking.html               # Package tracking detail page
│
├── data/
│   ├── products.js            # Product catalog with metadata (image, rating, price, keywords)
│   ├── cart.js                # Shopping cart state & operations
│   └── deliveryOptions.js     # Delivery speed/cost tiers (1-day, 3-day, 7-day)
│
├── scripts/
│   ├── amazon.js              # Product listing page logic
│   ├── checkout.js            # Checkout page entry point
│   ├── utils/
│   │   └── money.js           # Currency formatting utility
│   └── checkout/
│       ├── orderSummary.js    # Cart items + delivery option selection
│       └── paymentSummary.js  # Order total calculation
│
├── styles/
│   ├── shared/
│   │   ├── general.css        # Global typography, colors, spacing
│   │   └── amazon-header.css  # Header component styles
│   └── pages/
│       ├── amazon.css         # Product grid styling
│       ├── checkout/          # Checkout page styles
│       ├── orders.css         # Order history styling
│       └── tracking.css       # Tracking page styling
│
└── images/                    # Product images and icons
```

## 🔄 How It Works

The app is a multi-page experience that maintains state across pages:

1. **Product Catalog** (`amazon.html`)
   - Dynamically renders products from `data/products.js`
   - Users select quantity and click "Add to Cart"
   - Cart updates in memory and syncs to localStorage

2. **Shopping Cart** (`checkout.html`)
   - Displays all cart items with product details
   - Users can select delivery options (free 7-day, $4.99 3-day, $9.99 1-day)
   - Calculates and displays order total with taxes and shipping
   - Users can remove items or update delivery preferences

3. **Order History** (`orders.html`)
   - Shows past orders with dates and totals
   - Displays order items with delivery status
   - Links to package tracking page

4. **Order Tracking** (`tracking.html`)
   - Shows delivery progress (Preparing → Shipped → Delivered)
   - Displays estimated arrival date
   - Shows product details and tracking status

**State Persistence:** Cart data is stored in `localStorage`, persisting across browser sessions. The `cart` module exports functions for adding, removing, and updating items.

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, or Edge)
- (Optional) Node.js for running a local dev server

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/stevekimani757-dev/amazon-project.git
   cd amazon-project
   ```

2. **Run the app:**

   **Option A: Direct browser (simplest)**
   ```bash
   # Simply open the file directly
   open amazon.html
   # or double-click amazon.html in your file explorer
   ```

   **Option B: Local dev server**
   ```bash
   # Using Node.js
   npx http-server

   # Or using Python
   python -m http.server 8000

   # Then visit http://localhost:8000 in your browser
   ```

3. **Start shopping!**
   - Browse products on the home page
   - Add items to your cart
   - Proceed to checkout to select delivery options
   - View order history and track packages

## 📦 Key Features

✅ **Dynamic Product Grid** - Products rendered from JavaScript data objects  
✅ **Shopping Cart** - Add/remove items, select quantities  
✅ **Delivery Options** - Choose between 3 shipping speeds with different costs  
✅ **Order Calculations** - Automatic tax and shipping calculations  
✅ **Order History** - View past orders with delivery status  
✅ **Package Tracking** - Track order progress with visual timeline  
✅ **Responsive Design** - Mobile-friendly layout using CSS Grid and Flexbox  
✅ **Persistent Storage** - Cart data saved to localStorage  
✅ **ES6 Modules** - Clean, modular JavaScript architecture  

## 🧑‍💻 Development

### File Descriptions

**Data Layer** (`data/`)
- `products.js` - Hardcoded product catalog; each product has id, image, name, rating, price (in cents), keywords
- `cart.js` - Manages cart state (array of items); exports `addToCart()`, `removeFromCart()`, `updateDeliveryOption()`
- `deliveryOptions.js` - Defines 3 shipping tiers; exports `getDeliveryOption()`

**Utilities** (`scripts/utils/`)
- `money.js` - Single function `formatCurrency()` to convert cents to dollar strings

**UI Modules** (`scripts/checkout/`)
- `orderSummary.js` - Renders cart items and delivery option selectors
- `paymentSummary.js` - Renders order totals with tax and shipping

### Adding a New Product

Edit `data/products.js` and add an object to the `products` array:
```javascript
{
  id: "unique-uuid-here",
  image: "images/products/product-image.jpg",
  name: "Product Name",
  rating: { stars: 4.5, count: 127 },
  priceCents: 2995,  // $29.95
  keywords: ["category", "tag1", "tag2"]
}
```

### Customizing Styles

Global styles are in `styles/shared/general.css`. Page-specific styles are in `styles/pages/`.

## 🤝 Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is open source. Feel free to use it for learning, personal projects, or as a foundation for your own e-commerce site.

## 👤 Author

**stevekimani757-dev**  
- GitHub: [@stevekimani757-dev](https://github.com/stevekimani757-dev)

## 📞 Support

Have questions or found a bug? Open an [issue](https://github.com/stevekimani757-dev/amazon-project/issues) on the GitHub repository.

---

**Happy coding!** 🎉
