# 🚗 Car Rental Management System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/sanjana123-dot/car_rental/graphs/commit-activity)

A robust, full-stack web application designed to streamline the vehicle rental experience. Customers can easily discover and rent cars online, while admins manage fleet operations efficiently.

The Car Rental Management System offers a modern and user-friendly platform that eliminates paperwork and walk-in dependency. Users can browse a wide range of vehicles categorized by model, type, brand, price, and fuel efficiency. With secure authentication, customers can make reservations, track booking statuses, and manage their rental history from any device.

For rental agencies, this system provides powerful administrative tools to manage cars, bookings, customer details, and rental analytics. It ensures real-time availability management, preventing double bookings and optimizing fleet utilization.

This solution aims to improve service accessibility, enhance customer satisfaction, and boost rental business productivity through smart automation and digitalization.

---

## 📖 Table of Contents

- ✨ [Features](#-features)
- 🧑‍💻 [Tech Stack](#-tech-stack)
- 🏗️ [System Architecture](#-system-architecture)
- 🖥️ [Screenshots](#-screenshots)
- ⚙️ [Installation & Setup](#️-installation--setup)
- 🔌 [API Endpoints](#-api-endpoints)
- 📁 [Folder Structure](#-folder-structure)
- 🚀 [Future Enhancements](#-future-enhancements)
- 🤝 [Contributing](#-contributing)
- 📜 [License](#-license)

---

## ✨ Features

### 👤 Customer Features
- **Secure Authentication:** User registration and login using JWT (JSON Web Tokens).
- **Advanced Search & Filter:** Filter cars by brand, category (SUV, Sedan, Luxury), price range, and fuel type.
- **Real-time Booking:** Date-range selection with instant availability checks to prevent double booking.
- **User Dashboard:** View booking status (Pending/Confirmed/Completed) and rental history.
- **Payment Integration:** Secure checkout flow integrated with Stripe/PayPal.

### 🛠 Admin Features
- **Resource Management:** Full CRUD (Create, Read, Update, Delete) functionality for the car fleet.
- **Booking Overview:** Monitor all active rentals, revenue statistics, and user activities.
- **Inventory Tracking:** Update car availability, mileage, and maintenance status.
- **User Moderation:** Manage registered users and handle cancellation requests.

---

## 💻 Tech Stack

- **Frontend:** React.js (Hooks, Context API/Redux), Tailwind CSS, Axios.
- **Backend:** Node.js, Express.js.
- **Database:** MongoDB with Mongoose ODM.
- **Authentication:** JWT, Bcrypt.js for password hashing.
- **File Storage:** Cloudinary (for car images).
- **Deployment:** Vercel (Frontend), Render/Heroku (Backend).

---


--

## 📂 Project Folder Architecture
```bash
car-rental-management-system/
│
├── client/                        # Frontend (React / Next.js)
│   ├── public/                    # Static assets
│   ├── src/
│   │   ├── assets/                # Images, icons, styling assets
│   │   ├── components/            # Reusable components (Navbar, CarCard, Footer...)
│   │   ├── pages/                 # Screens (Home, Login, Bookings, Admin Dashboard...)
│   │   ├── context/               # State management (Context API / Redux)
│   │   ├── services/              # API service files using Axios
│   │   ├── hooks/                 # Custom React Hooks
│   │   ├── utils/                 # Helper functions
│   │   └── index.js               # App entry point
│   ├── .env                       # Client environment variables
│   ├── package.json
│   └── README.md
│
|─ server/                        # Backend (Node.js + Express.js)
│   ├── config/
│   │   └── db.js                  # MongoDB Connection Setup
│   ├── controllers/               # Business logic (Auth, Cars, Bookings)
│   ├── models/                    # MongoDB Schemas (User, Car, Booking)
│   ├── routes/                    # API Routes
│   ├── middleware/                # Auth & error handling middleware
│   ├── utils/                     # Helpers like Cloudinary config
│   ├── uploads/                   # Optional car image uploads
│   ├── .env                       # Server secret keys and DB URI
│   ├── server.js                  # Express app entry point
│   ├── package.json
│   ├── README.md
│
├── docs/                          # Architecture docs, diagrams, API docs
│   ├── architecture.png
│   ├── ER-diagram.png
│   └── API-reference.md
│
├── .gitignore
├── LICENSE
└── README.md                      # Root documentation
```
---

## ⚙️ Installation & Setup

### 🔧 Clone Repository
```bash
git clone https://github.com/sanjana123-dot/car_rental.git
```
📍 Install Dependencies
```bash
cd client
npm install

cd ../server
npm install
```
▶ Run Servers
```bash
# Frontend
npm start
```
```bash
# Backend
npm run dev
```
---

## 📌 API Endpoints

### 🔐 Authentication Routes
| Method | Endpoint | Description | Protected |
|--------|----------|-------------|----------|
| POST   | /api/auth/register | Register new user (Customer/Admin) | ❌ |
| POST   | /api/auth/login | Login user & receive JWT token | ❌ |
| GET    | /api/auth/me | Get logged-in user details | ✔ |

---

### 🚘 Car Management Routes
| Method | Endpoint | Description | Role |
|--------|----------|-------------|-----|
| GET    | /api/cars | Get all available cars | Customer/Admin |
| GET    | /api/cars/:id | Get car details by ID | Customer/Admin |
| POST   | /api/cars | Add a new car | Admin |
| PUT    | /api/cars/:id | Update car info | Admin |
| DELETE | /api/cars/:id | Remove car from fleet | Admin |

---

### 📅 Booking Routes
| Method | Endpoint | Description | Role |
|--------|----------|-------------|-----|
| POST   | /api/bookings | Create booking for a car | Customer |
| GET    | /api/bookings | Get all bookings (admin panel) | Admin |
| GET    | /api/bookings/user/:userId | Get bookings for a specific user | Customer |
| PUT    | /api/bookings/:id/status | Approve/Cancel booking | Admin |
| DELETE | /api/bookings/:id | Delete booking | Admin |

---

### 🧾 Payment Routes (Optional / If Integrated)
| Method | Endpoint | Description | Role |
|--------|----------|-------------|-----|
| POST   | /api/payments/create-order | Create payment order | Customer |
| POST   | /api/payments/verify | Verify payment | Customer |

---

### 🖼 Image Upload Routes (Optional for Cloudinary)
| Method | Endpoint | Description | Role |
|--------|----------|-------------|-----|
| POST   | /api/upload/car-image | Upload car image | Admin |

---

### ⚠ Error Responses (General)
```json
{
  "success": false,
  "message": "Something went wrong!"
}

```
## 🚀 Future Enhancements

- ✔ Live GPS car tracking  
- ✔ Mobile App (React Native)  
- ✔ Dynamic pricing based on demand  
- ✔ Loyalty rewards program  

---

## 🤝 Contributing

Contributions are welcome! Follow these steps:

1. Fork the repository  
2. Create your feature branch  
   ```bash
   git checkout -b feature-name
   ```
3 .Commit your changes
```Bash
git commit -m "Add new feature"
```
4. Push to the branch
```Bash
git push origin feature-name
```
5. Open a Pull Request 🎉

## 📄 License
This project is licensed under the MIT License.

⭐ If you like this project, don't forget to star the repository!
