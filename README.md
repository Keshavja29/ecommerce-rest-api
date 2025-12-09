# E-Commerce REST API

A comprehensive e-commerce REST API built with Django and Django REST Framework.

## Features

- **User Authentication** - JWT-based authentication
- **Product Management** - CRUD operations for products
- **Category Management** - Organize products by categories
- **Shopping Cart** - Add/remove items, update quantities
- **Order Processing** - Place orders, track status
- **Payment Integration Ready** - Razorpay/Stripe integration structure
- **Inventory Management** - Stock tracking
- **Search & Filter** - Advanced product search
- **Admin Panel** - Django admin for management

## Tech Stack

- Python 3.10+
- Django 4.2
- Django REST Framework
- PostgreSQL / SQLite
- JWT Authentication
- Swagger/OpenAPI Documentation

## Installation

```bash
# Clone repository
git clone https://github.com/Keshavja29/ecommerce-rest-api.git
cd ecommerce-rest-api

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Run server
python manage.py runserver
```

## API Endpoints

### Authentication
- `POST /api/auth/register/` - Register new user
- `POST /api/auth/login/` - Login user
- `POST /api/auth/refresh/` - Refresh JWT token

### Products
- `GET /api/products/` - List all products
- `POST /api/products/` - Create product (Admin)
- `GET /api/products/{id}/` - Get product details
- `PUT /api/products/{id}/` - Update product (Admin)
- `DELETE /api/products/{id}/` - Delete product (Admin)

### Categories
- `GET /api/categories/` - List categories
- `POST /api/categories/` - Create category (Admin)

### Cart
- `GET /api/cart/` - Get user's cart
- `POST /api/cart/add/` - Add item to cart
- `PUT /api/cart/update/{id}/` - Update cart item
- `DELETE /api/cart/remove/{id}/` - Remove from cart

### Orders
- `GET /api/orders/` - List user's orders
- `POST /api/orders/` - Create new order
- `GET /api/orders/{id}/` - Get order details

## Environment Variables

```
SECRET_KEY=your_django_secret_key
DEBUG=True
DATABASE_URL=postgresql://user:password@localhost/dbname
ALLOWED_HOSTS=localhost,127.0.0.1
```

## API Documentation

Access Swagger documentation at: `http://localhost:8000/api/docs/`

## Testing

```bash
python manage.py test
```

## Future Enhancements

- Payment gateway integration (Razorpay/Stripe)
- Email notifications
- Product reviews and ratings
- Wishlist functionality
- Coupon/discount system
- Advanced analytics

## License

MIT License
