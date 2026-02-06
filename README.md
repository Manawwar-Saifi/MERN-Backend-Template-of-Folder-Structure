# Project Structure

project-root/
│
├── .env.example # Environment variables template
├── .env.development # Development environment config
├── .env.production # Production environment config
├── .gitignore # Git ignore file
├── package.json # Node dependencies and scripts
├── README.md # Project documentation
├── server.js # Main application entry point
│
├── config/ # Configuration files
│ ├── index.js # Main config loader
│ ├── database.config.js # Database configuration
│ ├── cloudinary.config.js # Cloudinary setup
│ ├── payment.config.js # Payment gateway config
│ ├── email.config.js # Email service config
│ ├── redis.config.js # Redis / cache config
│ └── constants.js # App-wide constants
│
├── src/
│ ├── app.js # Express app initialization
│ │
│ ├── modules/ # Feature-based modules
│ │
│ │ ├── auth/
│ │ │ ├── auth.controller.js
│ │ │ ├── auth.service.js
│ │ │ ├── auth.routes.js
│ │ │ ├── auth.validation.js
│ │ │ └── auth.model.js
│ │
│ │ ├── user/
│ │ │ ├── user.controller.js
│ │ │ ├── user.service.js
│ │ │ ├── user.routes.js
│ │ │ ├── user.validation.js
│ │ │ └── user.model.js
│ │
│ │ ├── product/
│ │ │ ├── product.controller.js
│ │ │ ├── product.service.js
│ │ │ ├── product.routes.js
│ │ │ ├── product.validation.js
│ │ │ └── product.model.js
│ │
│ │ ├── order/
│ │ │ ├── order.controller.js
│ │ │ ├── order.service.js
│ │ │ ├── order.routes.js
│ │ │ ├── order.validation.js
│ │ │ └── order.model.js
│ │
│ │ ├── cart/
│ │ │ ├── cart.controller.js
│ │ │ ├── cart.service.js
│ │ │ ├── cart.routes.js
│ │ │ ├── cart.validation.js
│ │ │ └── cart.model.js
│ │
│ │ ├── payment/
│ │ │ ├── payment.controller.js
│ │ │ ├── payment.service.js
│ │ │ ├── payment.routes.js
│ │ │ ├── payment.validation.js
│ │ │ ├── payment.model.js
│ │ │ └── gateways/
│ │ │ ├── stripe.gateway.js
│ │ │ ├── paypal.gateway.js
│ │ │ ├── razorpay.gateway.js
│ │ │ └── gateway.interface.js
│ │
│ │ ├── cms/
│ │ │ ├── page/
│ │ │ ├── blog/
│ │ │ └── media/
│ │
│ │ ├── crm/
│ │ │ ├── customer/
│ │ │ ├── lead/
│ │ │ └── ticket/
│ │
│ │ ├── dashboard/
│ │ │ ├── dashboard.controller.js
│ │ │ ├── dashboard.service.js
│ │ │ ├── dashboard.routes.js
│ │ │ └── widgets/
│ │
│ │ ├── notification/
│ │ │ ├── notification.controller.js
│ │ │ ├── notification.service.js
│ │ │ ├── notification.routes.js
│ │ │ ├── notification.model.js
│ │ │ └── channels/
│ │
│ │ └── upload/
│ │ ├── upload.controller.js
│ │ ├── upload.service.js
│ │ ├── upload.routes.js
│ │ └── upload.validation.js
│ │
│ ├── middlewares/
│ ├── utils/
│ ├── services/
│ ├── database/
│ ├── routes/
│ └── validators/
│
├── public/
├── storage/
├── tests/
├── scripts/
└── docs/