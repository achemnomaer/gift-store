# Gift Store

Gift Store is a full-stack **eCommerce platform** built with **Django (backend) and Next.js (frontend)**. It features a seamless shopping experience with authentication, cart functionality, order management, and secure payments via Stripe.

## Features

- **User Authentication**: Secure login and signup system.
- **Product Listings**: Browse a variety of gifts with images and descriptions.
- **Cart & Checkout**: Add items to the cart, proceed to checkout, and complete payments.
- **Order Management**: Users can track their order history and manage addresses.
- **Wishlist**: Save favorite items for future purchases.
- **Stripe Payment Integration**: Secure online transactions.
- **Cloudinary Image Hosting**: Efficient media storage and delivery.

## Tech Stack

### **Frontend** (Next.js)
- React + Next.js
- Tailwind CSS for styling
- Axios for API requests
- Framer Motion for animations

### **Backend** (Django)
- Django & Django REST Framework (DRF)
- SQLite3 (default for local development)
- PostgreSQL (for production deployment)
- Stripe for payment processing
- Cloudinary for media storage
- JWT-based authentication

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/achemnomaer/gift-store.git
cd gift-store
```

### 2. Backend Setup (Django)
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env  # Update environment variables
python manage.py migrate
python manage.py runserver
```

### 3. Frontend Setup (Next.js)
```bash
cd frontend
npm install
npm run dev
```

## Environment Variables

Set up a `.env` file in both the backend and frontend directories.

### **Frontend (.env.local):**
```
NEXTAUTH_URL=http://127.0.0.1:3000/
NEXTAUTH_SECRET=
NEXTAUTH_BACKEND_URL=http://127.0.0.1:8000/api
NEXT_PUBLIC_BACKEND_URL=http://127.0.0.1:8000
NEXT_PUBLIC_REVALIDATION_TIME=5
NEXT_PUBLIC_STRIPE_PUBLIC_KEY=
```

### **Backend (.env):**
```
DJANGO_SECRET_KEY=
JWT_SECRET_KEY=
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1,mydomain.com,achemnomaer1959.pythonanywhere.com
CORS_ALLOWED_ORIGINS=https://localhost:3000
STRIPE_SECRET_KEY=
STRIPE_WEBHOOK_SECRET=
CHECKOUT_SUCCESS_URL=http://localhost:3000/checkout/success/
CHECKOUT_FAILED_URL=http://localhost:3000/checkout/failed/
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
SIGNING_KEY=
```

### How to Get the Required Credentials:
- **Django Secret Key**: Generate using `import secrets; print(secrets.token_urlsafe(50))` in a Python shell.
- **JWT Secret Key**: Generate a secure random key using an online tool or `openssl rand -hex 32`.
- **Stripe API Keys**: Sign up at [Stripe](https://stripe.com/) and get your secret/public keys from the developer dashboard.
- **Cloudinary API Credentials**: Create an account at [Cloudinary](https://cloudinary.com/) and get your cloud name, API key, and API secret.
- **NextAuth Secret**: Generate using `openssl rand -base64 32`.

## Deployment

- **Frontend**: Vercel / Netlify
- **Backend**: PythonAnywhere / Railway / Render
- **Database**: PostgreSQL (Cloud-based hosting like Railway, Supabase, or DigitalOcean)


