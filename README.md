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
