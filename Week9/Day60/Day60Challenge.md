## Day 60: Templates in Django

### Introduction to Django Templates

Templates in Django are used to define the structure and layout of your HTML files. They allow you to dynamically generate HTML content using the data passed from views. Templates help separate the presentation layer from the business logic, making it easier to manage and maintain your code.

### Creating and Using Templates

Let's create a simple template to display a welcome message.

#### Step 1: Create a Templates Directory

Inside your `blog` app directory, create a folder named `templates`, and inside it, create another folder named `blog`. This structure is recommended to keep templates organized by app.

```
blog/
    templates/
        blog/
            home.html
```

#### Step 2: Create a Template File

Create a file named `home.html` inside the `blog/templates/blog/` directory and add the following HTML code:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Blog Home</title>
</head>
<body>
    <h1>Welcome to the Blog Home!</h1>
</body>
</html>
```

#### Step 3: Modify the View to Use the Template

Update your view in `blog/views.py` to render the template instead of returning an `HttpResponse` directly:

```python
from django.shortcuts import render

def blog_home(request):
    return render(request, 'blog/home.html')
```

#### Step 4: Configure Template Directory in Settings

Make sure Django knows where to find your templates. In `myproject/settings.py`, ensure the `TEMPLATES` setting includes the `DIRS` key pointing to your templates directory:

```python
import os
# ...

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                # ...
            ],
        },
    },
]
```

### Template Inheritance and Extending Templates

Django templates support inheritance, which allows you to create a base template that other templates can extend. This is useful for maintaining a consistent layout across multiple pages.

#### Step 5: Create a Base Template

Create a file named `base.html` inside the `blog/templates/blog/` directory:

```html
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}My Blog{% endblock %}</title>
</head>
<body>
    <header>
        <h1>My Blog</h1>
    </header>
    <main>
        {% block content %}{% endblock %}
    </main>
    <footer>
        <p>&copy; 2024 My Blog</p>
    </footer>
</body>
</html>
```

#### Step 6: Extend the Base Template

Update `home.html` to extend `base.html`:

```html
{% extends "blog/base.html" %}

{% block title %}Blog Home{% endblock %}

{% block content %}
    <h1>Welcome to the Blog Home!</h1>
{% endblock %}
```

### Using Static Files in Templates

Static files such as CSS, JavaScript, and images are important for styling and enhancing the functionality of your web pages.

#### Step 7: Create a Static Directory

Inside your `blog` app directory, create a folder named `static`, and inside it, create another folder named `blog`:

```
blog/
    static/
        blog/
            style.css
```

Add the following CSS to `style.css`:

```css
body {
    font-family: Arial, sans-serif;
}

header {
    background-color: #f8f9fa;
    padding: 10px;
    text-align: center;
}

footer {
    background-color: #f8f9fa;
    padding: 10px;
    text-align: center;
    position: fixed;
    bottom: 0;
    width: 100%;
}
```

#### Step 8: Link Static Files in the Template

Update `base.html` to include the CSS file:

```html
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}My Blog{% endblock %}</title>
    <link rel="stylesheet" type="text/css" href="{% static 'blog/style.css' %}">
</head>
<body>
    <header>
        <h1>My Blog</h1>
    </header>
    <main>
        {% block content %}{% endblock %}
    </main>
    <footer>
        <p>&copy; 2024 My Blog</p>
    </footer>
</body>
</html>
```

Ensure the `STATIC_URL` is configured correctly in `myproject/settings.py`:

```python
STATIC_URL = '/static/'
```

### Assignment: Create a New Template and Use Static Files

1. **Create a new view in `blog/views.py` that returns a template named `post.html`.**
2. **Create the `post.html` template and extend the `base.html` template.**
3. **Add a new static file for additional styling and link it in the `base.html` template.**
4. **Run the server and test the new view and template by navigating to the appropriate URL.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)