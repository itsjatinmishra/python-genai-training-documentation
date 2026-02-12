# 🚀 Python with Generative AI – Learning Documentation
### By Jatin Mishra

---

## 📌 About This Documentation

This repository documents my learning journey in Full Stack Development using Python with Generative AI during my training at BTES (Bebo Technologies).

Technologies covered:
- Python
- HTML, CSS, JavaScript, Bootstrap
- Django
- Django REST Framework
- React
- JWT Authentication
- RAG Architecture
- FAISS
- OpenAI / LLM Integration

---

# 📚 3. Django Fundamentals

## 🔹 What is Django
- High level Python Web Framework
- Designed for fast, secure, scalable
- open-source & community-driven
- Follows MVT (Model-View-Template) architecture
- Moto: "The web framework for perfectionists with deadlines"

## 🔹 Key Features
- Batteries Included - Build-in tools for authentications, admin panel, ORM, etc.
- Scalable - From small apps to large-scale platforms
- Secure - Protects against SQL Injection, XSS, CSRF
- Cross-Platform - Works on Windows, Mac, Linux
- Strong Community Support - Large ecosystem of plugins and tutorials

## 🔹 Why Use Django ?
- Fast Development - Build project quickly
- Security - Inbuilt security best practices
- Scalability - Handles hight traffic and large datasets
- Built-in Admin Panel - Manage data without extra coding
- Reusable Code - Write once, use multiple times

Real World Use:

```python
Instagram - Socail Media
Pinterest - Image Sharing Platform
Mozilla - Add-ons Store

Also best for blog website, e-commerce websites and social media platforms

```

# 🔹 MVT Architecture in Django

---

## 📌 What is MVT?

**MVT (Model–View–Template)** is Django’s architectural pattern that separates:

- Data handling  - Model
- Business logic - View
- User Interface - Template

This separation helps in building clean, scalable, and maintainable applications.

---

## 📦 Components of MVT

### 1️⃣ Model

```python
# models.py
from django.db import models

class Student(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```
- Manages database structure
- Handles data logic
- Uses Django ORM

### 2️⃣ View

```python
# views.py
from django.shortcuts import render
from .models import Student

def student_list(request):
    students = Student.objects.all()
    return render(request, "students.html", {"students": students})
```
- Handles HTTP requests
- Connects Model and Template
- Contains business logic

### 3️⃣ Template

``` html
<!-- students.html -->
<h1>Student List</h1>
{% for student in students %}
  <p>{{ student.name }} - {{ student.age }}</p>
{% endfor %}
```

- Handles UI (HTML + Django Template Language)
- Displays dynamic data

## 🔄 MVT Flow
```text
User → URL → View → Model → Template → Response
```



# 🐍 Django Setup Guide (Windows)
### By Jatin Mishra

This documentation explains step-by-step how to:

- Install Python on Windows
- Install Django
- Create a Django Project
- Create an App
- Run the Development Server
- Setup Database & Admin Panel

---

# 🐍 1️⃣ Install Python on Windows

## Step 1: Download Python

Go to:

https://www.python.org/downloads/

Click **Download Python (Latest Version)**

---

## Step 2: Install Python

⚠️ IMPORTANT:

✔️ Check the box **"Add Python to PATH"**

Then click:

Install Now

---

## Step 3: Verify Installation

Open **Command Prompt (cmd)** and run:

```bash
python --version
```

OR

```bash
python -V
```

If installed correctly, you will see:

```
Python 3.x.x
```

---

# 📦 2️⃣ Check pip Installation

Run:

```bash
pip --version
```

If version appears → pip installed successfully ✅

---

# 📁 3️⃣ Create Project Folder

Move to Desktop (or preferred location):

```bash
cd Desktop
```

Create new folder:

```bash
mkdir django_projects
cd django_projects
```

---

# 🌱 4️⃣ Create Virtual Environment

Create virtual environment:

```bash
python -m venv venv
```

Activate virtual environment:

```bash
venv\Scripts\activate
```

If activated successfully, you will see:

```
(venv)
```

---

# 🚀 5️⃣ Install Django

Inside activated virtual environment:

```bash
pip install django
```

Check Django version:

```bash
django-admin --version
```

---

# 🏗️ 6️⃣ Create Django Project

Create project:

```bash
django-admin startproject myproject
```

Go inside project:

```bash
cd myproject
```

Project Structure:

```
myproject/
│
├── manage.py
└── myproject/
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    ├── asgi.py
    └── wsgi.py
```

---

# ▶️ 7️⃣ Run Development Server

Run:

```bash
python manage.py runserver
```

You will see:

```
Starting development server at http://127.0.0.1:8000/
```

Open browser and visit:

```
http://127.0.0.1:8000/
```

If Django welcome page appears → SUCCESS 🎉

---

# 📱 8️⃣ Create Django App

Inside project folder (where manage.py exists):

```bash
python manage.py startapp myapp
```

New structure:

```
myproject/
│
├── myapp/
├── myproject/
└── manage.py
```

---

# 🔗 9️⃣ Register App in settings.py

Open:

```
myproject/settings.py
```

Find:

```python
INSTALLED_APPS = [
```

Add your app:

```python
'myapp',
```

Example:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp',
]
```

Save the file.

---

# 🗄️ 🔟 Run Migrations (Database Setup)

Create migration files:

```bash
python manage.py makemigrations
```

Apply migrations:

```bash
python manage.py migrate
```

This sets up the database (SQLite by default).

---

# 👤 1️⃣1️⃣ Create Superuser (Admin Panel)

Run:

```bash
python manage.py createsuperuser
```

Enter:

- Username
- Email
- Password

Run server again:

```bash
python manage.py runserver
```

Visit:

```
http://127.0.0.1:8000/admin/
```

Login using superuser credentials.

Admin panel working successfully ✅

---

# 📌 Important Commands Summary

| Task | Command |
|------|----------|
| Create virtual environment | `python -m venv venv` |
| Activate venv | `venv\Scripts\activate` |
| Install Django | `pip install django` |
| Create project | `django-admin startproject myproject` |
| Run server | `python manage.py runserver` |
| Create app | `python manage.py startapp myapp` |
| Make migrations | `python manage.py makemigrations` |
| Apply migrations | `python manage.py migrate` |
| Create superuser | `python manage.py createsuperuser` |

---

# 🎯 Conclusion

You have successfully:

- Installed Python
- Installed Django
- Created a Django project
- Created an app
- Configured database
- Accessed admin panel

This documentation will be continuously updated as I grow in Full Stack Development and Generative AI 🚀
