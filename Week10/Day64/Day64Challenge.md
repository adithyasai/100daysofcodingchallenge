## Day 64: User Authentication Basics

### Introduction to Django’s Authentication System

Django comes with a built-in authentication system that handles user login, logout, password management, and user sessions. This system is highly customizable and can be extended to meet the specific needs of your application.

### Setting Up User Authentication

Today, we’ll learn how to set up user registration, login, and logout views in Django.

### Step 1: Create User Registration View

1. **Create a Registration Form:**

   Open `blog/forms.py` and create a registration form using Django’s built-in `UserCreationForm`:

   ```python
   from django import forms
   from django.contrib.auth.forms import UserCreationForm
   from django.contrib.auth.models import User

   class RegistrationForm(UserCreationForm):
       email = forms.EmailField(required=True)

       class Meta:
           model = User
           fields = ['username', 'email', 'password1', 'password2']
   ```

2. **Create the Registration View:**

   Open `blog/views.py` and create a view to handle user registration:

   ```python
   from django.shortcuts import render, redirect
   from django.contrib.auth import login, authenticate
   from .forms import RegistrationForm

   def register(request):
       if request.method == 'POST':
           form = RegistrationForm(request.POST)
           if form.is_valid():
               user = form.save()
               username = form.cleaned_data.get('username')
               password = form.cleaned_data.get('password1')
               user = authenticate(username=username, password=password)
               login(request, user)
               return redirect('blog_home')
       else:
           form = RegistrationForm()
       return render(request, 'blog/register.html', {'form': form})
   ```

3. **Create a Registration Template:**

   Create a template named `register.html` in the `blog/templates/blog/` directory:

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>User Registration</title>
   </head>
   <body>
       <h1>Register</h1>
       <form method="post">
           {% csrf_token %}
           {{ form.as_p }}
           <button type="submit">Register</button>
       </form>
   </body>
   </html>
   ```

4. **Add a URL Pattern for the Registration View:**

   Open `blog/urls.py` and add a URL pattern for the `register` view:

   ```python
   from django.urls import path
   from .views import blog_home, post_detail, register

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('register/', register, name='register'),
   ]
   ```

### Step 2: Create User Login and Logout Views

1. **Create Login and Logout Views:**

   Django provides built-in views for login and logout. You can use these views by adding the following URL patterns in `blog/urls.py`:

   ```python
   from django.contrib.auth import views as auth_views

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('register/', register, name='register'),
       path('login/', auth_views.LoginView.as_view(template_name='blog/login.html'), name='login'),
       path('logout/', auth_views.LogoutView.as_view(), name='logout'),
   ]
   ```

2. **Create Login and Logout Templates:**

   Create a template named `login.html` in the `blog/templates/blog/` directory:

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Login</title>
   </head>
   <body>
       <h1>Login</h1>
       <form method="post">
           {% csrf_token %}
           {{ form.as_p }}
           <button type="submit">Login</button>
       </form>
   </body>
   </html>
   ```

   For logout, you can redirect to the home page or display a simple message. The built-in logout view doesn’t require a template, but you can customize it if needed.

### Step 3: Restricting Access to Views

You can restrict access to certain views so that only authenticated users can access them.

1. **Use Login Required Decorator:**

   Open `blog/views.py` and import the `login_required` decorator:

   ```python
   from django.contrib.auth.decorators import login_required

   @login_required
   def create_post(request):
       if request.method == 'POST':
           form = PostForm(request.POST)
           if form.is_valid():
               # Process the form data
               title = form.cleaned_data['title']
               content = form.cleaned_data['content']
               # Save the data to the database
               Post.objects.create(title=title, content=content)
               return redirect('blog_home')
       else:
           form = PostForm()

       return render(request, 'blog/create_post.html', {'form': form})
   ```

2. **Update URL Pattern for the Create Post View:**

   Ensure the URL pattern for the `create_post` view is updated in `blog/urls.py`:

   ```python
   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('register/', register, name='register'),
       path('login/', auth_views.LoginView.as_view(template_name='blog/login.html'), name='login'),
       path('logout/', auth_views.LogoutView.as_view(), name='logout'),
       path('create/', create_post, name='create_post'),
   ]
   ```

### Assignment: Implement User Authentication

1. **Create a registration form and view.**
2. **Create login and logout views using Django’s built-in views.**
3. **Restrict access to the `create_post` view so that only authenticated users can access it.**
4. **Test the user registration, login, and logout functionality by navigating to the appropriate URLs.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)