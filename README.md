# E-commerce API Project
This is a Django REST API project for an e-commerce system that allows users to register, login, and manage their profiles, browse products and categories, and place orders. The project uses Redis for caching and Django Channels for real-time notifications.

Prerequisites
- Python 3.9 or higher
- Django 4.1 or higher
- PostgreSQL 13 or higher
- Redis 6 or higher

Setup
1. Clone the repository:

bash
git clone https://github.com/Karthik07-eng/Assignment-DRF-Enlog

2. Create a virtual environment and activate it:

bash
python -m venv venv
source venv/bin/activate

3. Install the required packages:

bash
pip install -r requirements.txt

4. Create a PostgreSQL database and user:

CREATE DATABASE ecommerce_db;
CREATE ROLE ecommerce_user WITH PASSWORD 'ecommerce_password';
GRANT ALL PRIVILEGES ON DATABASE ecommerce_db TO ecommerce_user;

5. Update the settings.py file with your database credentials:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'ecommerce_db',
        'USER': 'ecommerce_user',
        'PASSWORD': 'ecommerce_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

6. Run migrations:

bash
python manage.py migrate

7. Start the Redis server:

bash
redis-server

8. Start the Django development server:

bash
python manage.py runserver

9. Start the Django Channels worker:

bash
python manage.py runworker


API Endpoints
- POST /api/register/: Register a new user
- POST /api/login/: Login to obtain an access token
- GET /api/products/: Get a list of products
- GET /api/categories/: Get a list of categories
- POST /api/orders/: Place an order
- GET /api/orders/: Get a list of orders for the current user

Real-time Notifications
- When an order is placed, the user will receive a real-time notification when the order status changes.

Caching
- The project uses Redis to cache product and category data. The cache is invalidated when the data is updated.

Contributing
Contributions are welcome! Please submit a pull request with your changes.
