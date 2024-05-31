## Day 68: Project: Simple Blog Application (Part 2)

### Extending the Blog App with User Authentication

In this session, we’ll extend our blog application to include user authentication. We will implement features that allow users to register, log in, and create posts only if they are logged in.

### Step 1: User Registration

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
   <!-- blog/templates/blog/register.html -->
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
   from .views import blog_home, post_detail, create_post, register

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('create/', create_post, name='create_post'),
       path('register/', register, name='register'),
   ]
   ```

### Step 2: User Login and Logout

1. **Create Login and Logout Views:**

   Django provides built-in views for login and logout. You can use these views by adding the following URL patterns in `blog/urls.py`:

   ```python
   from django.contrib.auth import views as auth_views

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('create/', create_post, name='create_post'),
       path('register/', register, name='register'),
       path('login/', auth_views.LoginView.as_view(template_name='blog/login.html'), name='login'),
       path('logout/', auth_views.LogoutView.as_view(next_page='blog_home'), name='logout'),
   ]
   ```

2. **Create Login and Logout Templates:**

   Create a template named `login.html` in the `blog/templates/blog/` directory:

   ```html
   <!-- blog/templates/blog/login.html -->
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

### Step 3: Restricting Access to Create Posts

To restrict access to creating posts so that only authenticated users can create posts, you can use Django’s `login_required` decorator.

1. **Use Login Required Decorator:**

   Open `blog/views.py` and import the `login_required` decorator:

   ```python
   from django.contrib.auth.decorators import login_required

   @login_required
   def create_post(request):
       if request.method == 'POST':
           form = PostForm(request.POST, request.FILES)
           if form.is_valid():
               form.save()
               return redirect('blog_home')
       else:
           form = PostForm()
       return render(request, 'blog/create_post.html', {'form': form})
   ```

### Step 4: Adding User Profiles (Optional)

If you want to extend the functionality to include user profiles, you can create a `Profile` model.

1. **Define the Profile Model:**

   Open `blog/models.py` and define the `Profile` model:

   ```python
   from django.db import models
   from django.contrib.auth.models import User

   class Profile(models.Model):
       user = models.OneToOneField(User, on_delete=models.CASCADE)
       bio = models.TextField(blank=True)
       profile_pic = models.ImageField(upload_to='profile_pics/', null=True, blank=True)

       def __str__(self):
           return self.user.username
   ```

2. **Create and Apply Migrations:**

   Generate the migration file and apply it to create the `Profile` table in the database:

   ```bash
   python manage.py makemigrations blog
   python manage.py migrate
   ```

3. **Register the Profile Model:**

   Open `blog/admin.py` and register the `Profile` model:

   ```python
   from django.contrib import admin
   from .models import Profile

   admin.site.register(Profile)
   ```

4. **Create Profile Form and View (Optional):**

   If you want to create a form and view for updating profiles, you can follow the steps similar to creating posts and handle profile updates.

### Assignment: Implement User Authentication and Profile

1. **Implement user registration, login, and logout functionality using Django’s built-in views and forms.**
2. **Restrict access to the `create_post` view so that only authenticated users can access it.**
3. **Optionally, create a user profile model and add functionality to update user profiles.**
4. **Test the user authentication and profile functionality by registering, logging in, creating posts, and updating profiles.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)