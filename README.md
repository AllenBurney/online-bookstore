# Online Bookstore

A full-stack MERN (MongoDB, Express, React, Node.js) web application for an online bookstore. This application provides a platform for users to browse books, add them to a shopping cart, securely place orders, and allows administrators to manage the inventory.

## 🚀 Features

### For Users:
- **Browse & Search:** Explore a catalog of books, search by title, and filter by genres or "On Sale" status.
- **Sorting:** Sort books by newest arrivals.
- **Shopping Cart:** Add, remove, and update quantities of books in the cart.
- **Secure Authentication:** User registration and login powered by JWT (JSON Web Tokens) and bcrypt for password hashing.
- **Checkout & Order History:** Secure checkout process and a dedicated page to view past order history.

### For Administrators:
- **Admin Dashboard:** Access a protected administration panel.
- **Inventory Management:** Add new books, update existing book details, and delete books.
- **Sales Management:** Put books on sale with custom discounts and manage sale prices.
- **Order Tracking:** View all platform orders.

## 🛠️ Technology Stack

**Frontend:**
- **React.js** (via Create React App)
- **React Router DOM** for navigation
- **Tailwind CSS** for responsive styling
- **Context API** (AuthContext, CartContext) for state management
- **Axios** for API communication

**Backend:**
- **Node.js & Express.js** for the RESTful API
- **MongoDB & Mongoose** for the database schema and queries
- **JSON Web Tokens (JWT)** for secure user authentication
- **Bcrypt.js** for password encryption

## 🏗️ Project Structure

The project is structured into frontend and backend segments:
- `backend/` - Contains the Express server, Mongoose models (`Book`, `Order`, `User`, etc.), API routes (`authRoutes`, `bookRoutes`, `cartRoutes`, `orderRoutes`), and middleware.
- `frontend/` - Contains the React application components, routing logic, styling, and public assets.

## ⚙️ Installation & Setup

### Prerequisites
- [Node.js](https://nodejs.org/) installed
- A running [MongoDB](https://www.mongodb.com/) instance (local or MongoDB Atlas)

### 1. Clone the Repository
```bash
git clone <repository-url>
cd online-bookstore
```

### 2. Backend Setup
The backend relies on dependencies defined in the root `package.json` and a specific execution script in the `backend/` folder.

1. Install backend dependencies from the root directory:
   ```bash
   npm install
   ```
2. Navigate to the `backend` folder:
   ```bash
   cd backend
   ```
3. Create a `.env` file in the `backend/` directory and configure the environment variables:
   ```env
   MONGO_URI=your_mongodb_connection_string
   PORT=5000
   JWT_SECRET=your_jwt_secret_key
   ```
4. Start the backend server:
   ```bash
   npm start
   # or run 'node server.js'
   ```
   *The backend should default to `https://online-bookstore-wy1m.onrender.com`.*

### 3. Frontend Setup
1. Open a new terminal and navigate to the `frontend` directory:
   ```bash
   cd frontend
   ```
2. Install frontend dependencies:
   ```bash
   npm install
   ```
3. Start the React development server:
   ```bash
   npm start
   ```
   *The frontend should run on `http://localhost:3000`.*

## 🔒 Authentication Flow & Security
- Passwords are encrypted before being saved to the database.
- Upon successful login, the server issues a standard JSON Web Token (JWT).
- The token is securely sent on authorized requests to access protected functionality (e.g. creating orders, accessing admin panels).
- `authMiddleware` validates JWT integrity and an overarching `isAdmin` constraint protects administrative endpoints from normal users.
