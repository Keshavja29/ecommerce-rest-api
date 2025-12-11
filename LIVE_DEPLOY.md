# 🌐 LIVE DEPLOYMENT - E-Commerce REST API

## 🚀 Deploy to Railway (Easiest for Django)

### Step 1: Prepare for Deployment

**Create these files in your project:**

#### 1. `requirements.txt` (Already exists)
```txt
Django==4.2.5
djangorestframework==3.14.0
django-cors-headers==4.2.0
psycopg2-binary==2.9.7
gunicorn==21.2.0
python-decouple==3.8
Pillow==10.0.0
```

#### 2. `Procfile` (Create this)
```
web: gunicorn ecommerce.wsgi --log-file -
```

#### 3. `runtime.txt` (Create this)
```
python-3.11.5
```

---

### Step 2: Deploy on Railway

**1. Create Railway Account:**
- Visit: https://railway.app
- Click "Login with GitHub"
- Authorize Railway

**2. Create New Project:**
- Click "New Project"
- Select "Deploy from GitHub repo"
- Choose `ecommerce-rest-api`
- Click "Deploy Now"

**3. Add Environment Variables:**

Go to "Variables" tab and add:

```
DEBUG=False
SECRET_KEY=django-insecure-your-secret-key-here-change-this
ALLOWED_HOSTS=.railway.app
DATABASE_URL=postgresql://user:pass@host:5432/dbname
```

**4. Add PostgreSQL Database:**
- Click "New" → "Database" → "Add PostgreSQL"
- Railway will automatically set `DATABASE_URL`

**5. Deploy:**
- Railway will automatically deploy
- Wait 2-3 minutes
- Your API will be live!

**Your Live API:** `https://ecommerce-api.railway.app`

---

## 🎯 Alternative: Deploy to Render

### Step 1: Create Render Account
1. Visit: https://render.com
2. Sign up with GitHub

### Step 2: Create Web Service
1. Click "New +" → "Web Service"
2. Connect GitHub repository
3. Select `ecommerce-rest-api`

### Step 3: Configure:
- **Name:** ecommerce-api
- **Environment:** Python 3
- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `gunicorn ecommerce.wsgi:application`

### Step 4: Environment Variables:
```
PYTHON_VERSION=3.11.5
SECRET_KEY=your-secret-key
DEBUG=False
ALLOWED_HOSTS=.onrender.com
```

### Step 5: Add PostgreSQL:
- Click "New +" → "PostgreSQL"
- Connect to your web service

### Step 6: Deploy!
- Click "Create Web Service"
- Wait 5-10 minutes
- Done!

**Your Live API:** `https://ecommerce-api.onrender.com`

---

## 📱 Test Your Live API:

### Using Browser:
```
https://your-api-url.railway.app/api/products/
https://your-api-url.railway.app/api/categories/
https://your-api-url.railway.app/api/orders/
```

### Using Postman:
1. Download Postman: https://postman.com
2. Create new request
3. GET: `https://your-api-url.railway.app/api/products/`
4. Send request
5. See response!

---

## 🔧 Local Setup (For Development):

### Step 1: Install Python
1. Visit: https://python.org/downloads
2. Download Python 3.11
3. Install (check "Add to PATH")

### Step 2: Clone & Setup
```bash
# Clone repository
git clone https://github.com/Keshavja29/ecommerce-rest-api.git
cd ecommerce-rest-api

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Run server
python manage.py runserver
```

**Access locally:** `http://localhost:8000`

---

## 🎉 Your API is LIVE!

**API Endpoints:**
- Products: `/api/products/`
- Categories: `/api/categories/`
- Orders: `/api/orders/`
- Cart: `/api/cart/`
- Users: `/api/users/`

**Admin Panel:** `https://your-api-url.railway.app/admin`

---

## 📚 API Documentation:

Add this to your README:

```markdown
## Live API

**Base URL:** https://ecommerce-api.railway.app

### Endpoints:

#### Products
- GET `/api/products/` - List all products
- POST `/api/products/` - Create product
- GET `/api/products/{id}/` - Get product details
- PUT `/api/products/{id}/` - Update product
- DELETE `/api/products/{id}/` - Delete product

#### Authentication
- POST `/api/auth/register/` - Register user
- POST `/api/auth/login/` - Login user
- POST `/api/auth/logout/` - Logout user
```

---

## 🔄 Auto-Deploy:

Every time you push to GitHub:
- Railway/Render automatically redeploys
- No manual work needed!

```bash
git add .
git commit -m "Updated API"
git push origin main
# Automatically deploys! ✅
```

---

## 💡 Tips:

1. **Use Environment Variables** for secrets
2. **Enable CORS** for frontend access
3. **Add API Documentation** (Swagger/ReDoc)
4. **Monitor Logs** on Railway/Render dashboard
5. **Set up Custom Domain** (optional)

---

## 🎯 Next Steps:

1. ✅ Deploy API
2. ✅ Test endpoints
3. ✅ Add to portfolio
4. ✅ Share live link on resume
5. ✅ Connect frontend (if any)

**Your API is production-ready!** 🚀
