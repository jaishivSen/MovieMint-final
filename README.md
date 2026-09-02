# 🎬 MovieMint

> A full-stack movie booking platform built with the MERN stack, providing movie discovery, show management, seat selection, online booking, authentication, payments, and booking management.

[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react\&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-6-646CFF?logo=vite\&logoColor=white)](https://vitejs.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-Backend-339933?logo=node.js\&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5-000000?logo=express\&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?logo=mongodb\&logoColor=white)](https://www.mongodb.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?logo=tailwindcss\&logoColor=white)](https://tailwindcss.com/)
[![Stripe](https://img.shields.io/badge/Stripe-Payments-635BFF?logo=stripe\&logoColor=white)](https://stripe.com/)

---

## 📌 Overview

**MovieMint** is a full-stack movie booking web application designed to provide a complete movie discovery and ticket-booking experience.

Users can explore movies, view detailed movie information, select shows and seats, make bookings, and manage their bookings from a single platform.

The application follows a client-server architecture with a React-based frontend and a Node.js/Express backend connected to MongoDB.

---

## ✨ Features

### 👤 User Features

* 🔐 Secure user authentication with Clerk
* 🎬 Browse available movies
* 🔎 Explore movie details
* 🎞️ Watch movie trailers
* ❤️ Add movies to favorites
* 📅 Browse available shows
* 💺 Interactive seat selection
* 🎟️ Book movie tickets
* 💳 Online payment integration with Stripe
* 📋 View booking history
* 🔔 User-friendly toast notifications
* 📱 Responsive user interface

### 🛠️ Admin Features

* 👨‍💼 Admin dashboard
* 🎬 Manage movies
* 📅 Manage movie shows
* 🎟️ Manage bookings
* 👥 Manage users
* 📊 View application-related information

### ⚙️ Backend Features

* RESTful API architecture
* Authentication and authorization middleware
* MongoDB database integration using Mongoose
* Booking and show management
* Stripe payment integration
* Stripe webhook handling
* Cloudinary integration for media management
* Email functionality using Nodemailer
* Background/event-driven functionality using Inngest
* Environment-based configuration
* CORS configuration

---

## 🏗️ Tech Stack

### Frontend

| Technology      | Purpose                |
| --------------- | ---------------------- |
| React           | User interface         |
| Vite            | Frontend build tool    |
| Tailwind CSS    | Styling                |
| React Router    | Client-side routing    |
| Axios           | API communication      |
| Clerk           | Authentication         |
| React Player    | Trailer/video playback |
| Lucide React    | Icons                  |
| React Hot Toast | Notifications          |

### Backend

| Technology | Purpose                           |
| ---------- | --------------------------------- |
| Node.js    | Runtime environment               |
| Express.js | Backend framework                 |
| MongoDB    | Database                          |
| Mongoose   | MongoDB ODM                       |
| Clerk      | Authentication                    |
| Stripe     | Payment processing                |
| Cloudinary | Media management                  |
| Nodemailer | Email service                     |
| Inngest    | Background/event-driven functions |
| Axios      | External API requests             |
| CORS       | Cross-origin communication        |
| Dotenv     | Environment configuration         |

---

## 🧩 Project Architecture

MovieMint follows a **full-stack client-server architecture**:

```text
                    ┌──────────────────────┐
                    │      MovieMint       │
                    │    Web Application   │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │   React + Vite       │
                    │      Frontend        │
                    └──────────┬───────────┘
                               │
                         REST API / HTTP
                               │
                    ┌──────────▼───────────┐
                    │ Node.js + Express    │
                    │       Backend        │
                    └──────────┬───────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
       ┌──────▼──────┐  ┌──────▼──────┐  ┌────▼─────┐
       │   MongoDB   │  │    Stripe   │  │ Clerk    │
       │   Database  │  │   Payments  │  │   Auth   │
       └─────────────┘  └─────────────┘  └──────────┘
                               │
                     ┌─────────▼─────────┐
                     │    Cloudinary     │
                     │  Media Management │
                     └───────────────────┘
```

---

## 📂 Project Structure

```text
MovieMint-final/
│
├── client/
│   │
│   ├── public/
│   │
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── admin/
│   │   │   ├── BlurCircle.jsx
│   │   │   ├── DateSelect.jsx
│   │   │   ├── FeaturedSection.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── HeroSection.jsx
│   │   │   ├── Loading.jsx
│   │   │   ├── MovieCard.jsx
│   │   │   ├── Navbar.jsx
│   │   │   └── TrailersSection.jsx
│   │   │
│   │   ├── context/
│   │   ├── lib/
│   │   ├── pages/
│   │   │   ├── admin/
│   │   │   ├── Favorite.jsx
│   │   │   ├── Home.jsx
│   │   │   ├── MovieDetails.jsx
│   │   │   ├── Movies.jsx
│   │   │   ├── MyBookings.jsx
│   │   │   └── SeatLayout.jsx
│   │   │
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   ├── vite.config.js
│   └── vercel.json
│
├── server/
│   │
│   ├── configs/
│   ├── controllers/
│   │   ├── adminController.js
│   │   ├── bookingController.js
│   │   ├── showController.js
│   │   ├── stripeWebhooks.js
│   │   └── userController.js
│   │
│   ├── inngest/
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │   ├── Booking.js
│   │   ├── Movie.js
│   │   ├── Show.js
│   │   └── User.js
│   │
│   ├── routes/
│   │   ├── adminRoutes.js
│   │   ├── bookingRoutes.js
│   │   ├── showRoutes.js
│   │   └── userRoutes.js
│   │
│   ├── server.js
│   ├── package.json
│   └── vercel.json
│
└── README.md
```

---

## 🔐 Authentication

MovieMint uses **Clerk** for authentication.

Authentication is handled on both the frontend and backend, allowing protected application functionality to be accessed only by authenticated users.

The backend includes authentication middleware to protect API routes and verify authenticated requests.

---

## 💺 Seat Booking Flow

The movie booking process follows this general flow:

```text
Browse Movies
      ↓
Select Movie
      ↓
View Movie Details
      ↓
Select Show
      ↓
Choose Seats
      ↓
Review Booking
      ↓
Stripe Payment
      ↓
Booking Confirmation
      ↓
View My Bookings
```

---

## 💳 Payment Integration

MovieMint integrates **Stripe** to handle online payments.

The backend includes dedicated Stripe webhook handling so that payment-related events can be processed securely and booking information can be updated accordingly.

> ⚠️ Never commit real Stripe secret keys or other credentials to GitHub.

---

## ☁️ Cloudinary

Cloudinary is integrated into the backend for cloud-based media management.

This allows application media/assets to be stored and managed without keeping large media files directly inside the application server.

---

## 📧 Email Support

The backend uses **Nodemailer** for email-related functionality.

Email functionality can be used for application notifications and communication related to user activity.

---

## ⚡ Inngest

MovieMint includes **Inngest** integration for handling background/event-driven server-side functions.

This allows tasks that do not need to block the main request-response cycle to be processed separately.

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

* Node.js
* npm
* MongoDB account/database
* Clerk account
* Stripe account
* Cloudinary account
* Required API credentials

---

## 📥 Clone the Repository

```bash
git clone https://github.com/jaishivSen/MovieMint-final.git

cd MovieMint-final
```

---

# 🖥️ Frontend Setup

Navigate to the client directory:

```bash
cd client
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `client` directory.

Example:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASE_URL=your_backend_url
```

Start the frontend development server:

```bash
npm run dev
```

The Vite development server will start locally.

---

# ⚙️ Backend Setup

Open another terminal and navigate to the server:

```bash
cd server
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `server` directory.

Example:

```env
MONGODB_URI=your_mongodb_connection_string

CLERK_SECRET_KEY=your_clerk_secret_key

STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

SMTP_USER=your_email
SMTP_PASS=your_email_password
```

> The exact environment variable names should match the variables used in your backend source code.

Start the development server:

```bash
npm run server
```

Or start the production server:

```bash
npm start
```

---

## 🌐 Deployment

The project contains Vercel configuration files for both the frontend and backend.

The backend deployment is available through the project's configured Vercel deployment.

Before deploying, make sure all required environment variables are configured in the deployment platform.

---

## 🧪 Development Commands

### Client

```bash
npm run dev
```

Run the frontend development server.

```bash
npm run build
```

Create a production build.

```bash
npm run lint
```

Run ESLint checks.

```bash
npm run preview
```

Preview the production build locally.

### Server

```bash
npm run server
```

Start the backend with Nodemon.

```bash
npm start
```

Start the backend using Node.js.

---

## 🔒 Environment Variables

For security reasons, sensitive credentials should **never be committed to GitHub**.

Use `.env` files locally and configure environment variables through your deployment platform when deploying.

Recommended sensitive values include:

* Database connection strings
* Clerk secret keys
* Stripe secret keys
* Stripe webhook secrets
* Cloudinary credentials
* Email credentials
* API keys

---

## 📸 Screenshots

Add screenshots of the application here:

```text
screenshots/
├── home.png
├── movies.png
├── movie-details.png
├── seat-selection.png
├── booking.png
├── my-bookings.png
└── admin-dashboard.png
```

Example:

### 🏠 Home Page

![Home Page](screenshots/home.png)

### 🎬 Movie Details

![Movie Details](screenshots/movie-details.png)

### 💺 Seat Selection

![Seat Selection](screenshots/seat-selection.png)

### 🎟️ My Bookings

![My Bookings](screenshots/my-bookings.png)

---

## 🛣️ Future Enhancements

Potential improvements for future versions include:

* 📱 Dedicated mobile application
* 🔔 Push notifications
* ⭐ Movie reviews and ratings
* 🤖 Personalized movie recommendations
* 🎫 QR-code based ticket verification
* 📊 Advanced admin analytics
* 🎥 More detailed movie information
* 🌍 Multi-language support
* 🧾 Downloadable booking invoices
* 💬 User reviews and comments

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a new feature branch

```bash
git checkout -b feature/your-feature
```

3. Make your changes
4. Commit your changes

```bash
git commit -m "Add your feature"
```

5. Push the branch

```bash
git push origin feature/your-feature
```

6. Open a Pull Request

---

## 📄 License

This project is currently available for educational and development purposes.

If you plan to distribute or reuse the project, consider adding an appropriate open-source license such as the MIT License.

---

## 👨‍💻 Author

### Jai Shiv Sen

B.Tech Computer Science Engineering Student

GitHub: [@jaishivSen](https://github.com/jaishivSen)

---

## ⭐ Support

If you found this project useful or interesting, consider giving the repository a ⭐ on GitHub.

---

<p align="center">
  Made with ❤️ using React, Node.js, Express and MongoDB
</p>
