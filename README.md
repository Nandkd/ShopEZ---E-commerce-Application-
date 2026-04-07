# ShopEZ - E-commerce Application (MERN Stack)

A full-stack e-commerce application built with **MongoDB, Express.js, React.js, Node.js**.

---

## 🚀 Setup & Installation

### Prerequisites
- Node.js v18+
- MongoDB (local or Atlas)
- npm

---

### Step 1: Clone / Extract the project
```bash
cd shopez
```

### Step 2: Setup Backend

```bash
cd server
npm install
```

Edit `.env` file:
```
PORT=8000
MONGO_URI=mongodb://localhost:27017/shopez
JWT_SECRET=shopez_jwt_secret_key_2024
NODE_ENV=development
```

Seed the database (creates products + admin/user accounts):
```bash
node seed.js
```

Start the backend server:
```bash
npm run dev
# Server runs on http://localhost:8000
```

---

### Step 3: Setup Frontend

Open a new terminal:
```bash
cd client
npm install
npm start
# App runs on http://localhost:3000
```

---

## 🔐 Test Accounts (after seeding)

| Role  | Email                | Password   |
|-------|----------------------|------------|
| Admin | admin@shopez.com     | admin123   |
| User  | nand@shopez.com      | user123    |

---

## 📡 API Endpoints

### Auth
| Method | Endpoint              | Description        | Auth |
|--------|-----------------------|--------------------|------|
| POST   | /api/auth/register    | Register user      | No   |
| POST   | /api/auth/login       | Login user         | No   |
| GET    | /api/auth/profile     | Get own profile    | Yes  |

### Products
| Method | Endpoint              | Description        | Auth       |
|--------|-----------------------|--------------------|------------|
| GET    | /api/products         | Get all products   | No         |
| GET    | /api/products/:id     | Get single product | No         |
| POST   | /api/products         | Create product     | Admin only |
| PUT    | /api/products/:id     | Update product     | Admin only |
| DELETE | /api/products/:id     | Delete product     | Admin only |

### Cart
| Method | Endpoint              | Description        | Auth |
|--------|-----------------------|--------------------|------|
| GET    | /api/cart             | Get cart items     | Yes  |
| POST   | /api/cart             | Add to cart        | Yes  |
| DELETE | /api/cart/:id         | Remove item        | Yes  |
| DELETE | /api/cart/clear       | Clear cart         | Yes  |

### Orders
| Method | Endpoint              | Description        | Auth       |
|--------|-----------------------|--------------------|------------|
| POST   | /api/orders           | Place order        | Yes        |
| GET    | /api/orders/myorders  | My orders          | Yes        |
| GET    | /api/orders           | All orders         | Admin only |
| PUT    | /api/orders/:id       | Update status      | Admin only |

### Admin
| Method | Endpoint              | Description        | Auth       |
|--------|-----------------------|--------------------|------------|
| GET    | /api/admin/stats      | Dashboard stats    | Admin only |
| GET    | /api/admin/users      | All users          | Admin only |
| DELETE | /api/admin/users/:id  | Delete user        | Admin only |

---

## 🛠️ Tech Stack

- **Frontend:** React.js, React Router v6, Axios, Bootstrap 5
- **Backend:** Node.js, Express.js
- **Database:** MongoDB, Mongoose
- **Auth:** JWT, bcryptjs
- **Dev Tools:** nodemon

---

## ✨ Features

- User Registration & Login (JWT-based auth)
- Product listing with search, category & gender filters
- Product detail page with size/quantity selector
- Cart management (add, remove, clear)
- Checkout with shipping form & payment method selection
- Order placement & tracking
- User profile with order history
- Admin panel: Dashboard stats, Product CRUD, Order status management, User management
- Role-based access control (USER / ADMIN)
- Responsive design with Bootstrap 5
