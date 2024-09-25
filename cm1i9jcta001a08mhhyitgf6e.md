---
title: "Day 3. Getting Started with Django: Installing, Creating Your First Project, and Understanding the Structure"
datePublished: Wed Sep 25 2024 19:33:23 GMT+0000 (Coordinated Universal Time)
cuid: cm1i9jcta001a08mhhyitgf6e
slug: day-3-getting-started-with-django-installing-creating-your-first-project-and-understanding-the-structure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1727292723574/0117afd8-9d7f-4421-9f1c-2232c5f2e82d.png
tags: python, django, project-management, slice-of-code

---

Welcome to Day 3 of Django tutorial series! In this blog, we’ll go through installing Django, creating your first project and application, and exploring the project structure that Django generates. By the end of this tutorial, you'll have a solid foundation to start building your own web applications with Django.

## Installing Django

1. Activate Virtual Environment by following the steps from [Day 1.](https://simplykeep.in/day-1-prerequisites-and-best-practices#heading-step-2-activate-the-virtual-environment)
    
2. With your virtual environment activated, install Django using `pip`:
    

```bash
pip install django
```

This command downloads and installs the latest version of Django and its dependencies. For specific version use `pip install django==<version>`

## Creating Your First Django Project

Now that Django is installed, let's create a new project.

```bash
django-admin startproject projectpulse .
```

**Note**: The `.` at the end tells Django to create the project in the current directory./

### Understanding the Project Structure

After running the command, your directory should look like this:

```bash
project_mgmt/
├── manage.py
└── projectpulse/
    ├── __init__.py
    ├── asgi.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

Let's break down what each file does:

* [**manage.py**](http://manage.py): A command-line utility that lets you interact with your Django project in various ways (e.g., running the development server, creating apps, migrating databases).
    
* **projectpulse/**: The inner directory is your project's actual Python package.
    
    * **init.py**: An empty file that indicates this directory is a Python package.
        
    * [**asgi.py**](http://asgi.py): Entry-point for ASGI-compatible web servers to serve your project.
        
    * [**settings.py**](http://settings.py): Configuration settings for your project.
        
    * [**urls.py**](http://urls.py): The URL declarations for your project; a “table of contents” of your Django-powered site.
        
    * [**wsgi.py**](http://wsgi.py): Entry-point for WSGI-compatible web servers to serve your project.
        

Running the Development Server

To verify that everything is set up correctly, run the development server:

```bash
python manage.py runserver
```

You should see output similar to:

```bash
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
September 26, 2024 - 00:45:08
Django version 3.2, using settings 'projectpulse.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

Open your web browser and navigate to [http://127.0.0.1:8000/](http://127.0.0.1:8000/). You should see the D[j](http://127.0.0.1:8000/)ango "Welcome" page, indicating that your project is running successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727290805581/2db8fe24-ed4c-48ca-92ba-23fb014a660a.png align="center")

## Understanding Projects and Apps in Django

Before we proceed, it's crucial to understand the difference between a **project** and an **app** in Django.

### Projects

A **project** is the entire application, encompassing settings, configurations, and multiple apps. Think of it as the overarching container for your web application.

### Apps

An **app** is a web application that does something specific—for example, a blog system, a forum, or a poll application. Apps are reusable components that can be included in multiple projects.

**Key Points**:

* A project can contain multiple apps.
    
* An app can be part of multiple projects.
    

**website. A project can contain multiple apps. An app can be in multiple projects.**

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf_vLT2-eJvVDI3X_wkm13-poUql4mhcuE5ABjeEaOCYGRtQ0gbRqTQwaSbdC-5Mt4va1OA4qVwizJKVS3VzbxJ-KJCKr1Yo3LxL8FlhHAmtT_oXBMqYO_sJGnxgigcpP6bcPw1BI1fp_Hzs9npCAXWX_E?key=X03fU940uoMn2OECNbDIzQ align="left")

## Creating an Application

Let's create an app called `accounts`, which will handle user authentication and profiles.

```bash
python manage.py startapp accounts
```

Your directory structure now includes the `accounts` app:

```bash
accounts/
├── __init__.py
├── admin.py
├── apps.py
├── migrations/
│   └── __init__.py
├── models.py
├── tests.py
└── views.py
```

### Understanding the App Structure

* **init.py**: Indicates that this directory is a Python package.
    
* [**admin.py**](http://admin.py): Register your models here to make them accessible via Django's admin interface.
    
* [**apps.py**](http://apps.py): Configuration for the app.
    
* **migrations/**: Stores database migration files.
    
* [**models.py**](http://models.py): Define your database models here.
    
* [**tests.py**](http://tests.py): Write tests for your app here.
    
* [**views.py**](http://views.py): Handle the logic for processing requests and returning responses.
    

## Customizing the User Model

While Django provides a default `User` model, you might need to add extra fields like `profile_picture`, `address`, or `designation`. In such cases, it's better to create a custom user model.

### Why Create a Custom User Model?

* **Flexibility**: Add custom fields to suit your application's needs.
    
* **Future-Proofing**: Easier to make changes down the line.
    
* **Reusability**: Custom models can be reused across different projects.
    

### Approaches to Custom User Models

1. **AbstractUser**: Extends the existing Django `User` model.
    
2. **AbstractBaseUser**: Allows you to create a completely new user model from scratch.
    
3. **OneToOne** Mapping with Profile Model
    

For this tutorial, we'll use the `AbstractUser` approach to extend the existing user model. We'll cover the implementation details in our next blog post. For learning more on CustomUsers, you can check [How to Extend Django User Model](https://simpleisbetterthancomplex.com/tutorial/2016/07/22/how-to-extend-django-user-model.html)

## Conclusion

Congratulations! You've taken the first steps in your Django journey. Understanding the foundational structure of Django projects and apps sets you up for success as you build more complex applications. Stay tuned for the next post, where we'll enhance our `accounts` app with a custom user model.

## Additional Resources

* [Django Official Documentation](https://docs.djangoproject.com/en/4.2/)
    
* [Virtual Environments and Packages](https://docs.python.org/3/tutorial/venv.html)