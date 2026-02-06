# 🚀 MERN Backend Template

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)
![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white)

**A production-ready, scalable MERN backend boilerplate with enterprise-grade architecture**

[Features](#-features) • [Quick Start](#-quick-start) • [Architecture](#-architecture) • [Documentation](#-documentation) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

This is a **battle-tested, production-ready MERN backend template** designed for building **scalable, maintainable, and secure applications**. Perfect for startups, SaaS products, e-commerce platforms, CRM systems, and enterprise applications.

### ✨ What Makes This Special?

- 🏗️ **Modular Architecture** - Feature-based structure for easy scaling
- 🔐 **Security First** - JWT auth, rate limiting, input sanitization
- 💳 **Multi-Payment Gateway** - Stripe, PayPal, Razorpay integration
- 📁 **Cloud Storage Ready** - Centralized Cloudinary integration
- 🎯 **Clean Code** - Separation of concerns (Controller → Service → Model)
- ⚡ **Performance Optimized** - Redis caching, database indexing
- 🧪 **Test Ready** - Structured for unit, integration, and e2e tests
- 📊 **Production Ready** - Error handling, logging, environment configs

---

## 🌟 Features

### Core Functionality
- ✅ **Authentication & Authorization** - JWT-based auth with refresh tokens
- ✅ **User Management** - CRUD operations with role-based access control
- ✅ **E-commerce Ready** - Products, orders, cart, inventory management
- ✅ **Payment Processing** - Multiple gateway support (Stripe/PayPal/Razorpay)
- ✅ **CMS Capabilities** - Pages, blogs, media library management
- ✅ **CRM Features** - Customer management, leads, support tickets
- ✅ **Analytics Dashboard** - Real-time statistics and reporting
- ✅ **Notifications** - Email, SMS, and push notification channels
- ✅ **File Uploads** - Cloudinary integration with validation

### Technical Features
- 🔒 **Security** - Helmet, CORS, rate limiting, XSS protection
- 📝 **Validation** - Request validation with Joi/Yup schemas
- 🗄️ **Database** - MongoDB with Mongoose ODM, migrations support
- ⚡ **Caching** - Redis integration for performance
- 📊 **Logging** - Winston/Pino with multiple log levels
- 🔄 **Background Jobs** - Bull/BullMQ for async tasks
- 🌐 **API Versioning** - Structured route organization
- 📱 **RESTful API** - Best practices implementation

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|-------------|
| **Runtime** | Node.js (v16+) |
| **Framework** | Express.js |
| **Database** | MongoDB + Mongoose |
| **Authentication** | JWT (JSON Web Tokens) |
| **File Upload** | Cloudinary + Multer |
| **Caching** | Redis |
| **Payments** | Stripe, PayPal, Razorpay |
| **Email** | Nodemailer |
| **Validation** | Joi / Yup |
| **Testing** | Jest / Mocha |
| **Logging** | Winston / Pino |

---

## 🚀 Quick Start

### Prerequisites

```bash
- Node.js >= 16.x
- MongoDB >= 5.x
- Redis >= 6.x (optional, for caching)
- npm or yarn
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Manawwar-Saifi/MERN-Backend-Template-of-Folder-Structure.git
   cd MERN-Backend-Template-of-Folder-Structure
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Then edit `.env` with your configuration:
   ```env
   NODE_ENV=development
   PORT=5000
   
   # Database
   DB_HOST=localhost
   DB_PORT=27017
   DB_NAME=mern_app
   
   # JWT
   JWT_SECRET=your-super-secret-key-change-this
   JWT_EXPIRE=7d
   
   # Cloudinary
   CLOUDINARY_CLOUD_NAME=your-cloud-name
   CLOUDINARY_API_KEY=your-api-key
   CLOUDINARY_API_SECRET=your-api-secret
   ```

4. **Start the server**
   ```bash
   # Development
   npm run dev
   
   # Production
   npm start
   ```

5. **Seed the database** (optional)
   ```bash
   npm run seed
   ```

The server will start at `http://localhost:5000` 🎉

---

## 📁 Project Structure

```
project-root/
│
├── app.js                      # Express app configuration
├── server.js                   # Server entry point
├── package.json                # Dependencies and scripts
│
├── src/
│   ├── config/                 # Configuration files
│   │   ├── database.config.js  # Database settings
│   │   ├── cloudinary.config.js
│   │   ├── payment.config.js
│   │   └── constants.js
│   │
│   ├── modules/                # Feature modules
│   │   ├── auth/              # Authentication
│   │   ├── user/              # User management
│   │   ├── product/           # E-commerce products
│   │   ├── order/             # Order processing
│   │   ├── payment/           # Payment gateways
│   │   ├── cms/               # Content management
│   │   ├── crm/               # Customer relations
│   │   ├── dashboard/         # Analytics
│   │   └── upload/            # File uploads
│   │
│   ├── middlewares/           # Express middlewares
│   │   ├── auth.middleware.js
│   │   ├── error.middleware.js
│   │   ├── validation.middleware.js
│   │   └── rateLimiter.middleware.js
│   │
│   ├── services/              # Shared services
│   │   ├── cloudinary.service.js
│   │   ├── cache.service.js
│   │   └── queue.service.js
│   │
│   ├── utils/                 # Helper functions
│   │   ├── logger.js
│   │   ├── response.js
│   │   └── encryption.js
│   │
│   ├── database/              # Database setup
│   │   ├── connection.js
│   │   ├── migrations/
│   │   └── seeders/
│   │
│   └── routes/                # Route aggregation
│       └── index.js
│
├── storage/                   # Logs and temp files
│   ├── logs/
│   └── temp/
│
├── tests/                     # Test files
│   ├── unit/
│   ├── integration/
│   └── e2e/
│
└── docs/                      # Documentation
    ├── API.md
    └── SETUP.md
```

---

## 🏗️ Architecture

### Module-Based Design

Each feature is a self-contained module following this structure:

```
module/
├── controller.js    # HTTP request handlers
├── service.js       # Business logic
├── routes.js        # API endpoints
├── validation.js    # Input validation schemas
└── model.js         # Database schema
```

**Example: Authentication Module**

```javascript
// auth.controller.js - Handles HTTP requests
exports.login = async (req, res, next) => {
  const result = await authService.login(req.body);
  return response.success(res, result);
};

// auth.service.js - Business logic
exports.login = async (credentials) => {
  // Validate credentials, generate JWT
  const token = jwt.sign({ id: user._id }, JWT_SECRET);
  return { user, token };
};

// auth.routes.js - Route definitions
router.post('/login', validate(loginSchema), authController.login);
```

### Payment Gateway Abstraction

All payment gateways implement a common interface:

```javascript
// gateway.interface.js
class PaymentGateway {
  charge(amount, currency, metadata) { }
  refund(transactionId, amount) { }
  verifyWebhook(payload, signature) { }
}

// Usage
const gateway = PaymentGatewayFactory.create('stripe');
await gateway.charge(100, 'USD', orderData);
```

### Centralized Error Handling

```javascript
// throw from anywhere
throw new AppError('Resource not found', 404);

// Caught by error.middleware.js
app.use(errorMiddleware);
```

---

## 🔐 Security Features

- ✅ **JWT Authentication** - Secure token-based auth
- ✅ **Password Hashing** - Bcrypt encryption
- ✅ **Rate Limiting** - Prevent brute force attacks
- ✅ **CORS Protection** - Configured for frontend integration
- ✅ **Input Sanitization** - XSS and injection prevention
- ✅ **Helmet.js** - Security headers
- ✅ **Environment Variables** - Sensitive data protection
- ✅ **Request Validation** - Schema-based validation

---

## 📚 API Documentation

### Authentication Endpoints

```http
POST   /api/auth/register     # Register new user
POST   /api/auth/login        # Login user
POST   /api/auth/refresh      # Refresh JWT token
POST   /api/auth/logout       # Logout user
POST   /api/auth/forgot-password
POST   /api/auth/reset-password
```

### User Management

```http
GET    /api/users             # Get all users (admin)
GET    /api/users/:id         # Get user by ID
PUT    /api/users/:id         # Update user
DELETE /api/users/:id         # Delete user
```

### Products (E-commerce)

```http
GET    /api/products          # Get all products
POST   /api/products          # Create product (admin)
GET    /api/products/:id      # Get product details
PUT    /api/products/:id      # Update product
DELETE /api/products/:id      # Delete product
```

### Orders

```http
POST   /api/orders            # Create order
GET    /api/orders            # Get user orders
GET    /api/orders/:id        # Get order details
PUT    /api/orders/:id/status # Update order status
```

### Payments

```http
POST   /api/payments/stripe/charge
POST   /api/payments/paypal/charge
POST   /api/payments/razorpay/charge
POST   /api/payments/webhook  # Webhook endpoint
```

For complete API documentation, see [docs/API.md](docs/API.md)

---

## 🧪 Testing

```bash
# Run all tests
npm test

# Run unit tests
npm run test:unit

# Run integration tests
npm run test:integration

# Run with coverage
npm run test:coverage
```

### Test Structure

```javascript
// tests/unit/auth.test.js
describe('Auth Service', () => {
  it('should register a new user', async () => {
    const user = await authService.register(userData);
    expect(user).toHaveProperty('email');
  });
});
```

---

## 🌍 Environment Variables

Create a `.env` file in the root directory:

```env
# Server Configuration
NODE_ENV=development
PORT=5000
API_URL=http://localhost:5000

# Database
DB_TYPE=mongodb
DB_HOST=localhost
DB_PORT=27017
DB_NAME=mern_app
DB_USER=admin
DB_PASSWORD=password

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRE=7d
JWT_REFRESH_SECRET=your-refresh-token-secret
JWT_REFRESH_EXPIRE=30d

# Cloudinary
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=123456789012345
CLOUDINARY_API_SECRET=your-api-secret

# Payment Gateways
# Stripe
STRIPE_PUBLIC_KEY=pk_test_xxxxx
STRIPE_SECRET_KEY=sk_test_xxxxx
STRIPE_WEBHOOK_SECRET=whsec_xxxxx

# PayPal
PAYPAL_CLIENT_ID=xxxxx
PAYPAL_CLIENT_SECRET=xxxxx
PAYPAL_MODE=sandbox

# Razorpay
RAZORPAY_KEY_ID=rzp_test_xxxxx
RAZORPAY_KEY_SECRET=xxxxx

# Email Configuration
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
EMAIL_FROM=noreply@yourapp.com

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=

# Frontend URL
FRONTEND_URL=http://localhost:3000
```

---

## 📦 NPM Scripts

```json
{
  "start": "node server.js",
  "dev": "nodemon server.js",
  "test": "jest",
  "test:watch": "jest --watch",
  "test:coverage": "jest --coverage",
  "lint": "eslint .",
  "lint:fix": "eslint . --fix",
  "seed": "node scripts/seed.js",
  "migrate": "node scripts/migrate.js"
}
```

---

## 🎯 Usage Examples

### Creating a New Module

1. Create module folder: `src/modules/blog/`
2. Add required files:
   ```
   blog/
   ├── blog.controller.js
   ├── blog.service.js
   ├── blog.routes.js
   ├── blog.validation.js
   └── blog.model.js
   ```
3. Register routes in `src/routes/index.js`

### Adding a Payment Gateway

1. Create gateway file: `src/modules/payment/gateways/square.gateway.js`
2. Implement the interface:
   ```javascript
   class SquareGateway extends PaymentGateway {
     async charge(amount, currency, metadata) {
       // Implementation
     }
   }
   ```
3. Add credentials to `.env`

### Uploading Files to Cloudinary

```javascript
// In your controller
const cloudinaryService = require('@/services/cloudinary.service');

const result = await cloudinaryService.uploadImage(
  file.buffer, 
  'products',
  { width: 800, height: 800, crop: 'fill' }
);
```

---

## 🚢 Deployment

### Docker Deployment

```dockerfile
# Dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 5000
CMD ["node", "server.js"]
```

```bash
docker build -t mern-backend .
docker run -p 5000:5000 --env-file .env mern-backend
```

### Traditional Deployment

1. Set environment to production
2. Install dependencies: `npm ci --only=production`
3. Start server: `npm start`

**Recommended Platforms:**
- DigitalOcean
- AWS EC2
- Heroku
- Railway
- Render

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Style

- Follow existing architecture patterns
- Write meaningful commit messages
- Add tests for new features
- Update documentation

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Express.js community
- MongoDB documentation
- All open-source contributors

---

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Manawwar-Saifi/MERN-Backend-Template-of-Folder-Structure/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Manawwar-Saifi/MERN-Backend-Template-of-Folder-Structure/discussions)

---

<div align="center">

**⭐ If you find this template useful, please give it a star! ⭐**

Made with ❤️ by [Manawwar Saifi](https://github.com/Manawwar-Saifi)

</div>