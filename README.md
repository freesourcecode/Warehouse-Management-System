# Warehouse Management System in Django with Source Code

The **Warehouse Management System in Django** is created based on Python, Django, and SQLITE3 Database.

The admin can update the stock of the particular product, manage farmer, manage user and manage items.

It is an easy project for beginners to learn how to build a web-based python Django project.

We will provide you with the complete source code and database for the python project so that you can easily install it on your machine and learn how to program in Python Django.

>[!NOTE]
> To start creating a **Warehouse Management System Project in Python Django**, makes sure that you have PyCharm Professional IDE Installed in your computer.

## Admin Features

* **Login Page**

The page where the system administrator enters their system credentials in order to gain access to the system’s administrative side.

* **Manage farmers**

This is the page where an administrator can add, update, view and delete farmers information.

* **Manage stocks**

This is the page where an administrator can update a stocks.

* **Items Management**

This is the page where an administrator can add, update, view and delete items information.

* **New User Page**

The page where a new admin credentials are created by an admin.

* **Users list**

This is the page that lists and manages the added users.

## How to Create a Project Warehouse Management System Project in Django?

Here are the steps on how to create a **Warehouse Management System in Django** with Source Code.

1. **Open file**.

Open "pycharm professional" after that click "file" and click "new project".

2. **Choose Django**.

After click "new project", choose "Django" and click.

3. Select file location.

Then, select a file location wherever you want.

4. Create application name.

After that, name your application.

5. **Click create.**

Finish creating project by clicking “create” button.

6. **Start Coding**.

Finally, we will now start adding functionality to our Django Framework by adding some functional codes.

## Functionality and Codes of the Warehouse Management System Project in Django with Source Code

* **Create template for the store form in Warehouse Management System Project in Django**.

In this section, we will learn on how create a templates for the store form. 

To start with, add the following code in your store.html under the folder of store/templates/store.

``` {% extends 'basic/base.html' %}

{% block content %}
<div class="container" style="margin-top: 2%">
    <div class="row">
        <div class="col-lg-6" style="background-color: #324491; height: 200px; border-radius: 10px; float: left">
            <div style="display: flex; justify-content: center;">
            <h1 style="color: #8099dc;">
                <u>
                    Profile
                </u>
            </h1>
            </div>
            <div>
                {% for farmer in Farmer%}
            <h2 style="color: white">
                <b style="color: #202020">Name:-</b> {{farmer.user.username}}
            </h2>
            <h2 style="color: white">
                <b style="color: #202020">Phone No.:-</b> {{farmer.phone_number}}
            </h2>
            <h2 style="color: white">
                <b style="color: #202020">Address:-</b> {{farmer.address}}
            </h2>
            {% endfor %}
            </div>
        </div>
        <div class="col-lg-6" style="float:right; color: black">
            <h1 style="color: #26346d; float: right">
                <u><b>Total Inventory</b></u>
            </h1>
            <h4 style="float: right">
                {% for item, qnt in dict.items %}
                <p> {{item}} is available {{qnt}} units.</p>
                {% endfor %}
            </h4>
            <br><br><br>
            <h1 style="color: #26346d; float: right">
                <u><b>Your storages</b></u>
            </h1>
            <h4 style="float: right">
                {% for stock in dict2 %}
                <p> {{stock.item.name}} - {{stock.quantity}} stored on {{stock.stored_date}} </p>
                {% endfor %}
            </h4>
        </div>
    </div>
</div>
{% endblock %}
``` 

* **Create template for the homepage in Warehouse Management System Project in Django**.
In this section, we will learn on how create a templates for the homepage.

To start with, add the following code in your base.html under the folder of basic/templates/basic.

```{% load staticfiles %}

<html lang="en">
<head>
    <title>Warehouse</title>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="shortcut icon" type="image/png" href="{%  static 'icons/icon.png' %}"/>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">
    <link rel="stylesheet" href="{% static 'css/basic/basic.css' %}">
    <script src="https://use.fontawesome.com/f2c1d88751.js"></script>
    <style>
        body {
            background-color: skyblue;
            -webkit-background-size: cover;
            -moz-background-size: cover;
            -o-background-size: cover;
            background-size: cover;
            }
        @font-face {
            font-family: Liber;
            src: url('{% static 'fonts/Liber.ttf' %}') format("truetype");
            src: local('{% static 'fonts/Liber.ttf' %}') format("truetype");
            }
        .myfont{
                font-family: 'Liber', sans-serif;
            }
    </style>
</head>
<body>
    <nav class="navbar navbar-expand-lg navbar-light" style="background-color: black;">
        <a class="navbar-brand" href="{% url 'home_page'%}" style="color: #a2ffba; font-size:x-large ; font-family: Liber "Roboto", "Helvetica Neue", Helvetica, Arial, sans-serif">Myrel Food Warehouse</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'home_page' %}">
                        <i class="fa fa-home " aria-hidden="true"></i>
                        Home
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'store' %}">
                        <i class="fa fa-archive" aria-hidden="true"></i>
                        Store
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'sell' %}">
                        <i class="fa fa-money" aria-hidden="true"></i>
                        Sell
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'buy' %}">
                        <i class="fa fa-shopping-cart" aria-hidden="true"></i>
                        Buy
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'more' %}">
                        <i class="fa fa-info-circle" aria-hidden="true"></i>
                        More
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'about_us' %}">
                        <i class="fa fa-address-card" aria-hidden="true"></i>
                        About Us
                    </a>
                </li>
            </ul>
            <ul class="navbar-nav ml-auto">
                {% if user.is_authenticated %}
                    <li class="nav-item">
                        <a class="nav-link" style="color: red" href="{% url 'store' %}">
                            <i class="fa fa-user" aria-hidden="true"></i>
                            Hi, {{user.username}}
                        </a>
                    </li>
                {% else %}
                    <li class="nav-item">
                        <a class="nav-link" style="color: white" href="{% url 'login' %}">
                            <i class="fa fa-sign-in" aria-hidden="true"></i>
                            Login
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" style="color: white" href="{% url 'signup' %}">
                            <i class="fa fa-user-plus" aria-hidden="true"></i>
                            SignUp
                        </a>
                    </li>
                {% endif %}
                {% if user.is_authenticated %}
                <li class="nav-item">
                    <a class="nav-link" style="color: white" href="{% url 'logout' %}">
                        Logout
                        <i class="fa fa-power-off fa-lg" aria-hidden="true"></i>
                    </a>
                </li>
                {% endif %}
            </ul>
        </div>
    </nav>
    {% block content %}
    {% endblock %}

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.3/umd/popper.min.js" integrity="sha384-vFJXuSJphROIrBnz7yo7oB41mKfc8JzQZiCq4NCceLEaO4IHwicKwpJf9c9IpFgh" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/js/bootstrap.min.js" integrity="sha384-alpBpkh1PFOepccYVYDB4do5UnbKysX5WZXm3XxPqe5iKTfUKjNkCk9SaVuEZflJ" crossorigin="anonymous"></script>
</body>
</html>

```
## 📌Here's the full documentation for the [Warehouse Management System in Django](https://itsourcecode.com/free-projects/django/warehouse-management-system-project-in-django-with-source-code/)









