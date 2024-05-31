## Day 59: Django Apps

### Understanding Django Projects and Apps

In Django, a project is a collection of configuration and apps for a single website. An app is a web application that does something, like a blog, a forum, or a poll. A project can contain multiple apps, and an app can be part of multiple projects.

### Creating Your First Django App

Today, we’ll create a new app within our Django project and understand the difference between projects and apps.

#### Step 1: Create a New App

Navigate to your project directory and create a new app called `blog`:

```bash
python manage.py startapp blog
```

This will create a new directory called `blog` with the following structure:

```
blog/
    __init__.py
    admin.py
    apps.py
    models.py
    tests.py
    views.py
    migrations/
        __init__.py
```

#### Step 2: Register the App in Project Settings

To let Django know that your app is part of the project, you need to add it to the `INSTALLED_APPS` list in `myproject/settings.py`:

```python
INSTALLED_APPS = [
    ...
    'blog',
]
```

#### Step 3: Create Views in the App

Open `blog/views.py` and create a simple view:

```python
from django.http import HttpResponse

def blog_home(request):
    return HttpResponse("Welcome to the Blog Home!")
```

#### Step 4: Map Views to URLs

Next, we need to map our view to a URL. Open or create `blog/urls.py` and add the following code:

```python
from django.urls import path
from .views import blog_home

urlpatterns = [
    path('', blog_home, name='blog_home'),
]
```

Then include the `blog` URLs in the main project’s `urls.py`. Open `myproject/urls.py` and modify it:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('blog/', include('blog.urls')),
]
```

#### Step 5: Test the New App

Run the development server:

```bash
python manage.py runserver
```

Navigate to `http://127.0.0.1:8000/blog/` in your web browser. You should see the message "Welcome to the Blog Home!" displayed on the page.

### Assignment: Create Another View in the Blog App

1. **Create a new view in `blog/views.py` that returns "This is the blog post page!"**
2. **Add a URL pattern in `blog/urls.py` to map to this view at the path `post/`.**
3. **Run the server and test the new view by navigating to `http://127.0.0.1:8000/blog/post/`.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)