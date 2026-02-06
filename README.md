# Project Structure

# Universal Template - Folder & File Structure

```
project-root/
│
├── .env.example                          # Environment variables template
├── .env.development                      # Development environment config
├── .env.production                       # Production environment config
├── .gitignore                            # Git ignore file
├── package.json                          # Node dependencies and scripts
├── README.md                             # Project documentation
├── server.js                             # Main application entry point
│
├── config/                               # Configuration files
│   ├── index.js                          # Main config loader (loads env-specific configs)
│   ├── database.config.js                # Database connection configuration
│   ├── cloudinary.config.js              # Cloudinary setup and configuration
│   ├── payment.config.js                 # Payment gateway configurations
│   ├── email.config.js                   # Email service configuration
│   ├── redis.config.js                   # Redis/Cache configuration
│   └── constants.js                      # Application-wide constants
│
├── src/
│   ├── app.js                            # Express app setup with middlewares
│   │
│   ├── modules/                          # Feature-based modules
│   │   │
│   │   ├── auth/                         # Authentication module
│   │   │   ├── controller.js        # Login, register, logout controllers
│   │   │   ├── service.js           # Business logic for auth
│   │   │   ├── routes.js            # Auth routes definition
│   │   │   ├── validation.js        # Request validation schemas
│   │   │   └── model.js             # User model/schema
│   │   │
│   │   ├── user/                         # User management module
│   │   │   ├── controller.js        # CRUD operations for users
│   │   │   ├── service.js           # User business logic
│   │   │   ├── routes.js            # User routes
│   │   │   ├── validation.js        # User validation schemas
│   │   │   └── model.js             # User database model
│   │   │
│   │   ├── product/                      # E-commerce product module
│   │   │   ├── controller.js     # Product CRUD controllers
│   │   │   ├── service.js        # Product business logic
│   │   │   ├── routes.js         # Product routes
│   │   │   ├── validation.js     # Product validation
│   │   │   └── model.js          # Product schema
│   │   │
│   │   ├── order/                        # E-commerce order module
│   │   │   ├── controller.js       # Order management controllers
│   │   │   ├── service.js          # Order processing logic
│   │   │   ├── routes.js           # Order routes
│   │   │   ├── validation.js       # Order validation
│   │   │   └── model.js            # Order schema
│   │   │
│   │   ├── cart/                         # Shopping cart module
│   │   │   ├── controller.js        # Cart operations
│   │   │   ├── service.js           # Cart logic
│   │   │   ├── routes.js            # Cart routes
│   │   │   ├── validation.js        # Cart validation
│   │   │   └── model.js             # Cart schema
│   │   │
│   │   ├── payment/                      # Payment processing module
│   │   │   ├── controller.js     # Payment initiation & callback handling
│   │   │   ├── service.js        # Payment processing logic
│   │   │   ├── routes.js         # Payment routes
│   │   │   ├── validation.js     # Payment validation
│   │   │   ├── model.js          # Payment transaction schema
│   │   │   │
│   │   │   └── gateways/                 # Different payment gateway integrations
│   │   │       ├── stripe.js     # Stripe integration
│   │   │       ├── paypal.js     # PayPal integration
│   │   │       ├── razorpay.js   # Razorpay integration
│   │   │       └── gateway.interface.js  # Common interface for all gateways
│   │   │
│   │   ├── cms/                          # Content Management System module
│   │   │   ├── page/                     # CMS Pages
│   │   │   │   ├── controller.js    # Page CRUD
│   │   │   │   ├── service.js       # Page logic
│   │   │   │   ├── routes.js        # Page routes
│   │   │   │   ├── validation.js    # Page validation
│   │   │   │   └── model.js         # Page schema
│   │   │   │
│   │   │   ├── blog/                     # Blog/Articles
│   │   │   │   ├── controller.js    # Blog CRUD
│   │   │   │   ├── service.js       # Blog logic
│   │   │   │   ├── routes.js        # Blog routes
│   │   │   │   ├── validation.js    # Blog validation
│   │   │   │   └── model.js         # Blog schema
│   │   │   │
│   │   │   └── media/                    # Media library
│   │   │       ├── controller.js   # Media upload/management
│   │   │       ├── service.js      # Media processing logic
│   │   │       ├── routes.js       # Media routes
│   │   │       ├── validation.js   # Media validation
│   │   │       └── model.js        # Media schema
│   │   │
│   │   ├── crm/                          # Customer Relationship Management
│   │   │   ├── customer/                 # Customer management
│   │   │   │   ├── controller.js
│   │   │   │   ├── service.js
│   │   │   │   ├── routes.js
│   │   │   │   ├── validation.js
│   │   │   │   └── model.js
│   │   │   │
│   │   │   ├── lead/                     # Lead management
│   │   │   │   ├── controller.js
│   │   │   │   ├── service.js
│   │   │   │   ├── routes.js
│   │   │   │   ├── validation.js
│   │   │   │   └── model.js
│   │   │   │
│   │   │   └── ticket/                   # Support tickets
│   │   │       ├── controller.js
│   │   │       ├── service.js
│   │   │       ├── routes.js
│   │   │       ├── validation.js
│   │   │       └── model.js
│   │   │
│   │   ├── dashboard/                    # Dashboard & Analytics module
│   │   │   ├── controller.js   # Dashboard data aggregation
│   │   │   ├── service.js      # Analytics and reporting logic
│   │   │   ├── routes.js       # Dashboard routes
│   │   │   └── widgets/                  # Reusable dashboard widgets
│   │   │       ├── sales.js       # Sales statistics
│   │   │       ├── user.js        # User statistics
│   │   │       └── order.js       # Order statistics
│   │   │
│   │   ├── notification/                 # Notification module
│   │   │   ├── controller.js
│   │   │   ├── service.js
│   │   │   ├── routes.js
│   │   │   ├── model.js
│   │   │   └── channels/                 # Different notification channels
│   │   │       ├── email.js      # Email notifications
│   │   │       ├── sms.js        # SMS notifications
│   │   │       └── push.js       # Push notifications
│   │   │
│   │   └── upload/                       # File upload module (Cloudinary)
│   │       ├── controller.js      # File upload endpoints
│   │       ├── service.js         # Upload processing logic
│   │       ├── routes.js          # Upload routes
│   │       └── validation.js      # File validation
│   │
│   ├── middlewares/                      # Centralized middleware
│   │   ├── auth.middleware.js            # JWT authentication middleware
│   │   ├── error.middleware.js           # Global error handling middleware
│   │   ├── validation.middleware.js      # Request validation middleware
│   │   ├── upload.middleware.js          # File upload middleware (Multer/Cloudinary)
│   │   ├── rateLimiter.middleware.js     # Rate limiting middleware
│   │   ├── logger.middleware.js          # Request logging middleware
│   │   ├── cors.middleware.js            # CORS configuration middleware
│   │   ├── permission.middleware.js      # Role-based access control
│   │   └── sanitize.middleware.js        # Input sanitization middleware
│   │
│   ├── utils/                            # Utility functions
│   │   ├── logger.js                     # Winston/Pino logger setup
│   │   ├── response.js                   # Standardized API response formatter
│   │   ├── encryption.js                 # Encryption/Decryption utilities
│   │   ├── token.js                      # JWT token generation/verification
│   │   ├── email.js                      # Email sending utility
│   │   ├── sms.js                        # SMS sending utility
│   │   ├── pagination.js                 # Pagination helper
│   │   ├── validator.js                  # Custom validation functions
│   │   ├── fileHelper.js                 # File manipulation utilities
│   │   └── date.js                       # Date formatting utilities
│   │
│   ├── services/                         # Shared services
│   │   ├── cloudinary.service.js         # Centralized Cloudinary operations
│   │   ├── cache.service.js              # Redis caching service
│   │   ├── queue.service.js              # Job queue service (Bull/BullMQ)
│   │   └── search.service.js             # Search service (Elasticsearch/Algolia)
│   │
│   ├── database/                         # Database related files
│   │   ├── connection.js                 # Database connection setup
|   |   ├── mongodb.connection.js         # Mongodb Database connection setup
|   |   ├── sql.connection.js             # SQL Database connection setup
│   │   ├── migrations/                   # Database migrations
│   │   │   └── .gitkeep
│   │   └── seeders/                      # Database seeders
│   │       ├── user.seeder.js            # Sample user data
│   │       ├── product.seeder.js         # Sample product data
│   │       └── index.js                  # Master seeder
│   │
│   ├── routes/                           # Route aggregation
│   │   └── index.js                      # Combines all module routes
│   │
│   └── validators/                       # Shared validation schemas
│       ├── common.validation.js          # Common validation rules
│       └── custom.validation.js          # Custom validation rules
│
├── public/                               # Static files
│   ├── uploads/                          # Temporary upload folder (if not using Cloudinary)
│   ├── assets/                           # Public assets
│   │   ├── images/
│   │   ├── css/
│   │   └── js/
│   └── .gitkeep
│
├── storage/                              # Application storage
│   ├── logs/                             # Application logs
│   │   ├── error.log                     # Error logs
│   │   ├── combined.log                  # All logs
│   │   └── .gitkeep
│   └── temp/                             # Temporary files
│       └── .gitkeep
│
├── tests/                                # Test files
│   ├── unit/                             # Unit tests
│   │   ├── auth.test.js
│   │   ├── user.test.js
│   │   └── product.test.js
│   ├── integration/                      # Integration tests
│   │   ├── order.test.js
│   │   └── payment.test.js
│   ├── e2e/                              # End-to-end tests
│   │   └── checkout.test.js
│   └── setup.js                          # Test configuration
│
├── scripts/                              # Utility scripts
│   ├── seed.js                           # Database seeding script
│   ├── migrate.js                        # Migration runner
│   └── cleanup.js                        # Cleanup script
│
└── docs/                                 # Documentation
    ├── API.md                            # API documentation
    ├── SETUP.md                          # Setup instructions
    ├── DEPLOYMENT.md                     # Deployment guide
    └── ARCHITECTURE.md                   # Architecture overview
```


# MERN Backend Template – Scalable Folder Structure

A **production-ready MERN backend boilerplate** designed for **scalability, maintainability, and clean architecture**.  
This template follows **feature-based modular architecture**, making it ideal for **startups, SaaS products, and enterprise applications**.

---

## 🚀 Features

- Feature-based modular structure
- Clean separation of concerns (Controller, Service, Routes, Validation, Model)
- Ready for large-scale applications
- Supports Auth, CMS, CRM, Payments, Dashboard, Notifications, Uploads
- Environment-based configuration
- Easily extendable for new modules
- Follows best practices used in real-world production systems

---

## 🛠 Tech Stack

- **Node.js**
- **Express.js**
- **MongoDB / Mongoose**
- **JWT Authentication**
- **Cloudinary**
- **Redis**
- **Payment Gateways (Stripe, PayPal, Razorpay)**

---

## 📁 Project Structure Overview

```text
project-root/
This repository follows a layered + module-based architecture, explained below.

🌍 Root Level Files
File	Purpose
.env.example	Template for required environment variables
.env.development	Environment variables for development
.env.production	Environment variables for production
.gitignore	Files/folders ignored by Git
package.json	Project dependencies and scripts
README.md	Project documentation
server.js	Application entry point
⚙️ Configuration (/config)

Handles all application-level configuration.

File	Purpose
index.js	Loads environment-specific configurations
database.config.js	Database connection settings
cloudinary.config.js	Cloudinary initialization
payment.config.js	Payment gateway credentials
email.config.js	Email service configuration
redis.config.js	Redis caching configuration
constants.js	Application-wide constants
🧠 Application Source (/src)
app.js

Initializes Express app, middlewares, routes, and global error handlers.

🧩 Modules (/src/modules)

Each module is self-contained and includes:

Controller

Service

Routes

Validation

Model

🔐 Auth Module (/auth)

Handles authentication and authorization.

File	Purpose
auth.controller.js	Login, register, logout APIs
auth.service.js	Authentication business logic
auth.routes.js	Auth routes
auth.validation.js	Request validation schemas
auth.model.js	User schema
👤 User Module (/user)

User management and profile handling.

🛒 Product Module (/product)

Product CRUD operations for e-commerce or catalogs.

📦 Order Module (/order)

Order creation, processing, and management.

🛍 Cart Module (/cart)

User shopping cart operations.

💳 Payment Module (/payment)

Handles payment workflows and gateway integrations.

Gateways (/payment/gateways)
File	Purpose
stripe.gateway.js	Stripe integration
paypal.gateway.js	PayPal integration
razorpay.gateway.js	Razorpay integration
gateway.interface.js	Common gateway interface
📝 CMS Module (/cms)

Content management functionality.

Pages

Blogs

Media Library

Each section includes controller, service, routes, validation, and model.

📞 CRM Module (/crm)

Customer relationship management.

Customers

Leads

Support Tickets

📊 Dashboard Module (/dashboard)

Aggregated analytics and reporting.

Folder	Purpose
widgets/	Reusable dashboard widgets (sales, users, orders)
🔔 Notification Module (/notification)

Handles system notifications.

Channels

Email

SMS

Push Notifications

📤 Upload Module (/upload)

Centralized file upload handling (Cloudinary/Multer).

🧱 Middlewares (/middlewares)

Reusable Express middlewares.

File	Purpose
auth.middleware.js	JWT authentication
error.middleware.js	Global error handler
validation.middleware.js	Request validation
upload.middleware.js	File upload handling
rateLimiter.middleware.js	API rate limiting
logger.middleware.js	Request logging
cors.middleware.js	CORS configuration
permission.middleware.js	Role-based access
sanitize.middleware.js	Input sanitization
🧰 Utilities (/utils)

Helper functions used across the app.

Examples:

Logger

JWT handling

Encryption

Pagination

Email & SMS helpers

🔁 Shared Services (/services)

Used across multiple modules.

Service	Purpose
cloudinary.service.js	Central Cloudinary operations
cache.service.js	Redis caching
queue.service.js	Background jobs
search.service.js	Search engine integration
🗄 Database (/database)
Folder	Purpose
connection.js	Database connection
migrations/	DB migrations
seeders/	Sample data seeders
🚦 Routes (/routes)

Combines and registers all module routes.

✅ Validators (/validators)

Shared validation schemas across modules.

🌐 Public (/public)

Static assets and uploads.

🗃 Storage (/storage)

Logs and temporary files.

🧪 Tests (/tests)

Unit tests

Integration tests

End-to-end tests

🔧 Scripts (/scripts)

Utility scripts for:

DB seeding

Migrations

Cleanup tasks

📚 Docs (/docs)

Project documentation:

API reference

Setup guide

Deployment guide

Architecture overview

🏁 Getting Started
npm install
npm run dev

🤝 Contributing

Pull requests are welcome.
Please follow the existing architecture and naming conventions.



# File Descriptions & Purpose

## Root Files

### .env.example
Template for environment variables with placeholder values. Copy to .env for local development.

### package.json
Node.js dependencies, scripts for dev/production, and project metadata.

### server.js
Application entry point. Initializes database, starts Express server, handles graceful shutdown.

---

## Config Directory

### config/index.js
Loads appropriate config based on NODE_ENV (development/production/test).

### config/database.config.js
MongoDB/PostgreSQL/MySQL connection strings, pool settings, retry logic.

### config/cloudinary.config.js
Cloudinary credentials (cloud_name, api_key, api_secret), upload presets, folder structure.

### config/payment.config.js
Stores all payment gateway credentials (Stripe, PayPal, Razorpay), webhook secrets, currency settings.

### config/email.config.js
SMTP settings, email templates path, sender details.

### config/redis.config.js
Redis connection, TTL defaults, key prefixes.

---

## Modules (Feature-Based Architecture)

### modules/auth/*
- **controller**: Handles register, login, logout, refresh token, forgot password
- **service**: Password hashing, token generation, user verification logic
- **routes**: POST /register, /login, /logout, /refresh
- **validation**: Email format, password strength, required fields
- **model**: User schema with password encryption

### modules/payment/*
- **controller**: Initiates payment, handles webhooks, verifies transactions
- **service**: Processes payments through selected gateway, updates order status
- **gateways/**: Each gateway file implements common interface (charge, refund, verify)

### modules/cms/page/*
- **controller**: CRUD for dynamic pages (About, Contact, Terms)
- **service**: Slug generation, SEO metadata handling
- **model**: Page schema with title, slug, content, meta fields

### modules/crm/customer/*
- **controller**: Customer CRUD, activity logs, notes
- **service**: Customer segmentation, lifetime value calculation
- **model**: Customer schema with contact info, purchase history

### modules/dashboard/*
- **controller**: Aggregates data from multiple modules
- **widgets/**: Individual widget services (sales.widget.js returns sales metrics)

### modules/upload/*
- **controller**: Handles multipart/form-data uploads
- **service**: Calls cloudinary.service.js, stores metadata in DB
- **routes**: POST /upload (single/multiple files)

---

## Middlewares (Centralized)

### middlewares/auth.middleware.js
Verifies JWT token from header, attaches user to request object, handles unauthorized errors.

### middlewares/error.middleware.js
**GLOBAL ERROR HANDLER**: Catches all errors, formats response, logs stack trace, handles operational vs programmer errors.

### middlewares/validation.middleware.js
Validates request body/params/query against Joi/Yup schemas, returns 400 with field errors.

### middlewares/upload.middleware.js
Configures Multer for memory storage, file type validation, size limits before Cloudinary upload.

### middlewares/rateLimiter.middleware.js
Prevents abuse: limits requests per IP (e.g., 100 req/15min), uses Redis for distributed systems.

### middlewares/permission.middleware.js
Role-based access control (RBAC): checks user.role against required permissions.

---

## Utils (Helpers)

### utils/logger.js
Winston/Pino setup for logging to files/console with levels (error, warn, info, debug).

### utils/response.js
Standardized API responses:
```js
success(res, data, message, statusCode)
error(res, message, statusCode, errors)
```

### utils/encryption.js
Bcrypt for password hashing, AES for sensitive data encryption.

### utils/token.js
JWT sign/verify functions, refresh token generation.

### utils/pagination.js
Calculates skip/limit, formats paginated response with totalPages, currentPage.

---

## Services (Shared Business Logic)

### services/cloudinary.service.js
**CENTRALIZED CLOUDINARY**: Upload, delete, transform images, generate URLs, manage folders.
```js
uploadImage(buffer, folder, options)
deleteImage(publicId)
getOptimizedUrl(publicId, transformations)
```

### services/cache.service.js
Redis wrapper: get, set, delete, invalidate patterns, cache-aside pattern.

### services/queue.service.js
Bull/BullMQ for background jobs: email sending, report generation, image processing.

---

## Database

### database/connection.js
Establishes DB connection, handles reconnection logic, exports connection instance.

### database/seeders/*
Populates DB with initial/test data for development.

---

## Routes

### routes/index.js
Aggregates all module routes:
```js
app.use('/api/auth', authRoutes)
app.use('/api/products', productRoutes)
app.use('/api/orders', orderRoutes)
```

---

## Environment Variables (.env.example)

```env
# Server
NODE_ENV=development
PORT=5000
API_URL=http://localhost:5000

# Database
DB_TYPE=mongodb
DB_HOST=localhost
DB_PORT=27017
DB_NAME=myapp
DB_USER=admin
DB_PASSWORD=secret

# JWT
JWT_SECRET=your-secret-key
JWT_EXPIRE=7d
JWT_REFRESH_SECRET=refresh-secret
JWT_REFRESH_EXPIRE=30d

# Cloudinary
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

# Payment - Stripe
STRIPE_PUBLIC_KEY=pk_test_xxxxx
STRIPE_SECRET_KEY=sk_test_xxxxx
STRIPE_WEBHOOK_SECRET=whsec_xxxxx

# Payment - PayPal
PAYPAL_CLIENT_ID=xxxxx
PAYPAL_CLIENT_SECRET=xxxxx
PAYPAL_MODE=sandbox

# Payment - Razorpay
RAZORPAY_KEY_ID=rzp_test_xxxxx
RAZORPAY_KEY_SECRET=xxxxx

# Email
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-password
EMAIL_FROM=noreply@yourapp.com

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:3000
```

---

## Key Architecture Patterns

### 1. Module-Based Structure
Each feature (auth, product, order) is self-contained with its own controller, service, routes, validation, and model.

### 2. Centralized Error Handling
All errors caught by `error.middleware.js`. Use `AppError` class to throw errors:
```js
throw new AppError('Product not found', 404)
```

### 3. Payment Gateway Abstraction
All payment gateways implement common interface in `gateway.interface.js`:
- `charge(amount, currency, metadata)`
- `refund(transactionId, amount)`
- `verifyWebhook(payload, signature)`

### 4. Cloudinary Centralization
Never call Cloudinary directly from controllers. Always use `cloudinary.service.js` for consistent folder structure, naming, and error handling.

### 5. Environment-Based Config
All configs loaded through `config/index.js` which selects appropriate file based on NODE_ENV.

---

## Usage Examples

### Using Different Payment Gateways
```js
// In payment.service.js
const gateway = PaymentGatewayFactory.create(gatewayName) // 'stripe' | 'paypal' | 'razorpay'
const result = await gateway.charge(amount, currency, orderData)
```

### Uploading to Cloudinary
```js
// In upload.controller.js
const cloudinaryService = require('@/services/cloudinary.service')
const result = await cloudinaryService.uploadImage(file.buffer, 'products', {
  transformation: { width: 800, height: 800, crop: 'fill' }
})
```

### Standardized API Response
```js
// In product.controller.js
const products = await productService.getAll()
return response.success(res, products, 'Products fetched successfully')
```
