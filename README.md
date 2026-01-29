# 🏥 Doctor Appointment Booking System

A full-stack **Doctor Appointment Booking System** that allows patients to book appointments with doctors, manage their profiles, and make payments. The system includes an admin panel for managing doctors and appointments.

---

## ✨ Features

### 👤 Patient Features
- **User Authentication** - Secure login and registration
- **Browse Doctors** - View doctors by specialty
- **Book Appointments** - Select available time slots and book appointments
- **Manage Appointments** - View, track, and cancel appointments
- **Payment Integration** - Pay appointment fees via Stripe/Razorpay
- **Profile Management** - Update personal information

### 👨‍⚕️ Doctor Features
- **Doctor Dashboard** - View scheduled appointments
- **Manage Availability** - Update available time slots
- **Appointment Management** - Mark appointments as completed

### 🔧 Admin Features
- **Admin Dashboard** - Overview of system statistics
- **Manage Doctors** - Add, edit, and remove doctors
- **View All Appointments** - Monitor all appointments in the system
- **Doctor Availability Control** - Toggle doctor availability status

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|------------|---------|
| **Node.js** | Runtime environment |
| **Express.js** | Web framework |
| **MongoDB** | Database |
| **Mongoose** | ODM for MongoDB |
| **JWT** | Authentication |
| **Bcrypt** | Password hashing |
| **Cloudinary** | Image storage |
| **Multer** | File upload handling |
| **Stripe/Razorpay** | Payment processing |

### Frontend & Admin Panel
| Technology | Purpose |
|------------|---------|
| **React 18** | UI library |
| **Vite** | Build tool |
| **React Router** | Navigation |
| **Axios** | HTTP client |
| **Tailwind CSS** | Styling |
| **React Toastify** | Notifications |

---

## 📁 Project Structure

```
Doctor-Appointment/
├── backend/                 # Express.js API server
│   ├── config/              # Database configuration
│   ├── controllers/         # Route handlers
│   ├── middleware/          # Auth & upload middleware
│   ├── models/              # Mongoose schemas
│   │   ├── userModel.js     # User schema
│   │   ├── doctorModel.js   # Doctor schema
│   │   └── appointmentModel.js # Appointment schema
│   ├── routes/              # API routes
│   │   ├── adminRoute.js    # Admin endpoints
│   │   ├── doctorRoute.js   # Doctor endpoints
│   │   └── userRoute.js     # User endpoints
│   └── server.js            # Entry point
├── frontend/                # Patient-facing React app
│   └── src/
│       ├── components/      # Reusable UI components
│       ├── pages/           # Route pages
│       ├── context/         # React context
│       └── assets/          # Static assets
└── admin/                   # Admin panel React app
    └── src/
        ├── components/      # Admin UI components
        ├── pages/           # Admin route pages
        │   ├── Admin/       # Admin-specific pages
        │   └── Doctor/      # Doctor-specific pages
        └── context/         # Admin context
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v18 or higher)
- **MongoDB** (local or MongoDB Atlas)
- **Cloudinary** account (for image uploads)
- **Stripe/Razorpay** account (for payments)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Doctor-Appointment
   ```

2. **Install Backend Dependencies**
   ```bash
   cd backend
   npm install
   ```

3. **Install Frontend Dependencies**
   ```bash
   cd ../frontend
   npm install
   ```

4. **Install Admin Panel Dependencies**
   ```bash
   cd ../admin
   npm install
   ```

### Environment Variables

Create a `.env` file in the `backend/` directory:

```env
# MongoDB
MONGODB_URI=your_mongodb_connection_string

# JWT
JWT_SECRET=your_jwt_secret_key

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Payment (Stripe)
STRIPE_SECRET_KEY=your_stripe_secret_key

# Payment (Razorpay)
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret

# Admin Credentials
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=admin_password
```

### Running the Application

1. **Start the Backend Server**
   ```bash
   cd backend
   npm run server    # Development with nodemon
   # or
   npm start         # Production
   ```

2. **Start the Frontend**
   ```bash
   cd frontend
   npm run dev
   ```

3. **Start the Admin Panel**
   ```bash
   cd admin
   npm run dev
   ```

### Default Ports
| Service | Port |
|---------|------|
| Backend API | `http://localhost:4000` |
| Frontend | `http://localhost:5173` |
| Admin Panel | `http://localhost:5174` |

---

## 📡 API Endpoints

### User Routes (`/api/user`)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/register` | Register new user |
| POST | `/login` | User login |
| GET | `/appointments` | Get user appointments |
| POST | `/book-appointment` | Book an appointment |
| POST | `/cancel-appointment` | Cancel an appointment |
| POST | `/payment-stripe` | Process Stripe payment |
| POST | `/payment-razorpay` | Process Razorpay payment |

### Doctor Routes (`/api/doctor`)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/login` | Doctor login |
| GET | `/appointments` | Get doctor's appointments |
| POST | `/complete-appointment` | Mark appointment complete |
| POST | `/cancel-appointment` | Cancel appointment |
| GET | `/dashboard` | Get dashboard stats |
| POST | `/update-profile` | Update doctor profile |

### Admin Routes (`/api/admin`)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/login` | Admin login |
| POST | `/add-doctor` | Add new doctor |
| GET | `/all-doctors` | Get all doctors |
| GET | `/appointments` | Get all appointments |
| POST | `/change-availability` | Toggle doctor availability |
| GET | `/dashboard` | Get admin dashboard stats |

---

## 🔐 Authentication

The system uses **JWT (JSON Web Tokens)** for authentication:
- Tokens are generated upon successful login
- Protected routes require valid token in request headers
- Separate authentication for Users, Doctors, and Admins

---

## 💳 Payment Integration

The system supports two payment gateways:
- **Stripe** - For international payments
- **Razorpay** - For Indian payments

Payments are processed after appointment confirmation.

---

## 🖼️ Image Upload

Doctor profile images are uploaded and stored using **Cloudinary**:
- Images are uploaded via the admin panel
- Cloudinary provides CDN-optimized image URLs
- Multer handles multipart form data

---

## 📱 Responsive Design

Both the frontend and admin panel are fully responsive and optimized for:
- 📱 Mobile devices
- 📊 Tablets
- 💻 Desktops

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

Built with ❤️ for seamless doctor appointment booking experience.
