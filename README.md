Basics To Start Django Project

**Create Virtual Environment:**
bash
Copy code
# On Windows
python -m venv venv

# Activate the Virtual Environment:
## On Windows:
.\venv\Scripts\activate
## On macOS/Linux:
source venv/bin/activate
Install Django:
bash
Copy code
**pip install django**
Create a Django Project:
bash
Copy code
**django-admin startproject nameofproject**
Initialize Git Repository Locally:
bash
Copy code
**cd nameofproject**
**git init**
Stage and Commit Changes Locally:
bash
Copy code
**git add .**
**git commit -m "feat(feature): added initial project structure"**
Create a Git Repository on GitHub:
Create a new repository on GitHub (or any other Git hosting service).
Link Local and Remote Repository:
bash
Copy code
**git remote add origin https://github.com/yourusername/nameofproject.git**
Push Code to GitHub:
bash
Copy code
**git push -u origin main**
Development Workflow:
Continue developing your project, create Django apps, write business logic in views, define API endpoints in urls.py, and use Django models for database interactions.

Create a Django App:
bash
Copy code
**python manage.py startapp appname**

MVT Structure in Django:
Model:
python
Copy code
# models.py in your app

from django.db import models

class Post(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()

    def __str__(self):
        return self.title
View:
python
Copy code
# views.py in your app
from django.shortcuts import render
from .models import Post

def post_list(request):
    posts = Post.objects.all()
    return render(request, 'appname/post_list.html', {'posts': posts})
Template (post_list.html):


html
Copy code


<!DOCTYPE html>
<html>
<head>
    <title>Post List</title>
</head>
<body>
    <h1>Post List</h1>
    {% for post in posts %}
        <h2>{{ post.title }}</h2>
        <p>{{ post.content }}</p>
    {% endfor %}
</body>
</html>
Workflow Recap:
After creating the app and defining models, views, and templates, you can run the development server:
bash
Copy code
**python manage.py runserver**
