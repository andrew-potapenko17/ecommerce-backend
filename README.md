# 🛒 E-Commerce REST API Backend

A production-ready RESTful API backend for an e-commerce platform, built with **Django** and **Django REST Framework**. Handles product management, order processing, media uploads, and payment integration via Stripe.

---

## 🚀 Tech Stack

| Layer | Technology |
|---|---|
| Framework | Django 6.0 + Django REST Framework 3.17 |
| Database | PostgreSQL (production) / SQLite (development) |
| Payments | Stripe |
| Media | Pillow (image processing) |
| Server | Gunicorn + WhiteNoise |
| Config | python-dotenv |

---

## 📁 Project Structure

```
ecommerce-backend/
├── apiApp/                  # Core app — models, views, serializers, URLs
├── ecommerceApiProject/     # Django project settings & root URL config
├── media/                   # Uploaded media files (product images, etc.)
├── manage.py
├── requirements.txt
└── db.sqlite3               # Dev database (not used in production)
```

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/andrew-potapenko17/ecommerce-backend.git
cd ecommerce-backend
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the root directory:

```env
SECRET_KEY=your_django_secret_key
DEBUG=True
DATABASE_URL=postgresql://user:password@localhost:5432/ecommerce_db
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

### 5. Apply migrations

```bash
python manage.py migrate
```

### 6. Create a superuser

```bash
python manage.py createsuperuser
```

### 7. Run the development server

```bash
python manage.py runserver
```

---

## 💳 Payments

This project integrates **Stripe** for secure payment processing. Configure your Stripe keys in the `.env` file. Webhook handling is supported for real-time payment event processing.

---

## 🗄️ Database

- **Development:** SQLite (`db.sqlite3`) — zero config, works out of the box
- **Production:** PostgreSQL via `psycopg2-binary` — configure `DATABASE_URL` in `.env`

---

## 🖼️ Media Files

Product images and other uploads are stored in the `media/` directory. In production, **WhiteNoise** handles static file serving efficiently without a separate web server.

---

## 🌐 Production Deployment

This project is production-ready with **Gunicorn** as the WSGI server:

```bash
gunicorn ecommerceApiProject.wsgi:application --bind 0.0.0.0:8000
```

---

## 📦 Key Dependencies

```
Django==6.0.5
djangorestframework==3.17.1
psycopg2-binary==2.9.12
stripe==15.1.0
pillow==12.2.0
gunicorn==26.0.0
whitenoise==6.12.0
python-dotenv==1.2.2
```

---

## 📬 API Endpoints

Base URL: `/api/`

> Full API documentation coming soon. You can explore all endpoints via the Django admin panel at `/admin/` or use tools like **Postman** or **Insomnia** to interact with the API.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Andrew Potapenko**  
[GitHub](https://github.com/andrew-potapenko17)
