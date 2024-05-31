## Day 63: Project: Simple Blog Application (Part 1)

### Setting Up a New Django Project for a Blog

Today, we’ll start building a simple blog application. This project will help you apply the concepts you’ve learned so far, including setting up a Django project, creating apps, models, views, and templates.

### Step 1: Set Up a New Django Project

1. **Create a New Project:**

   Open your terminal and navigate to the directory where you want to create the project. Run the following command:

   ```bash
   django-admin startproject blogproject
   ```

2. **Navigate to the Project Directory:**

   ```bash
   cd blogproject
   ```

3. **Create a New App:**

   Inside the project directory, create a new app called `blog`:

   ```bash
   python manage.py startapp blog
   ```

4. **Register the App:**

   Add the `blog` app to the `INSTALLED_APPS` list in `blogproject/settings.py`:

   ```python
   INSTALLED_APPS = [
       ...
       'blog',
   ]
   ```

### Step 2: Designing the Blog’s Data Model

We will create a `Post` model to represent the blog posts.

1. **Define the Post Model:**

   Open `blog/models.py` and define the `Post` model:

   ```python
   from django.db import models

   class Post(models.Model):
       title = models.CharField(max_length=200)
       content = models.TextField()
       created_at = models.DateTimeField(auto_now_add=True)
       updated_at = models.DateTimeField(auto_now=True)

       def __str__(self):
           return self.title
   ```

2. **Create and Apply Migrations:**

   Generate the migration file and apply it to create the `Post` table in the database:

   ```bash
   python manage.py makemigrations blog
   python manage.py migrate
   ```

### Step 3: Creating Views and Templates for Displaying Blog Posts

We’ll create views to display a list of blog posts and individual post details.

1. **Create Views:**

   Open `blog/views.py` and create views for the blog home and post details:

   ```python
   from django.shortcuts import render, get_object_or_404
   from .models import Post

   def blog_home(request):
       posts = Post.objects.all()
       return render(request, 'blog/home.html', {'posts': posts})

   def post_detail(request, post_id):
       post = get_object_or_404(Post, id=post_id)
       return render(request, 'blog/post_detail.html', {'post': post})
   ```

2. **Create URL Patterns:**

   Open `blog/urls.py` and add URL patterns for the views:

   ```python
   from django.urls import path
   from .views import blog_home, post_detail

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
   ]
   ```

   Include the `blog` URLs in the main project’s `urls.py`:

   ```python
   from django.contrib import admin
   from django.urls import path, include

   urlpatterns = [
       path('admin/', admin.site.urls),
       path('blog/', include('blog.urls')),
   ]
   ```

3. **Create Templates:**

   Create the templates directory structure and the templates for the views:

   ```
   blog/
       templates/
           blog/
               home.html
               post_detail.html
   ```

   **home.html:**

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Blog Home</title>
   </head>
   <body>
       <h1>Blog Home</h1>
       <ul>
           {% for post in posts %}
               <li>
                   <a href="{% url 'post_detail' post.id %}">{{ post.title }}</a>
                   <p>{{ post.content|truncatewords:30 }}</p>
               </li>
           {% endfor %}
       </ul>
   </body>
   </html>
   ```

   **post_detail.html:**

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>{{ post.title }}</title>
   </head>
   <body>
       <h1>{{ post.title }}</h1>
       <p>{{ post.content }}</p>
       <p>Published on: {{ post.created_at }}</p>
       <a href="{% url 'blog_home' %}">Back to Home</a>
   </body>
   </html>
   ```

### Assignment: Populate the Database and Test the Application

1. **Create Some Blog Posts:**

   Use the Django admin interface or the Django shell to create a few blog posts. Ensure the `Post` model is registered in `blog/admin.py`:

   ```python
   from django.contrib import admin
   from .models import Post

   admin.site.register(Post)
   ```

2. **Run the Server and Test the Application:**

   Start the development server and navigate to `http://127.0.0.1:8000/blog/` to see the list of blog posts. Click on a post title to view its details.

   ```bash
   python manage.py runserver
   ```

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)