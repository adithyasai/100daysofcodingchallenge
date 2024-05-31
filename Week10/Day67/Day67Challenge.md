## Day 67: Working with Forms

### Advanced Form Handling in Django

Today, we will dive deeper into Django forms, exploring advanced form handling techniques. We will learn about `ModelForm`, customizing form fields, validation, and handling form submission.

### Using ModelForm

Django’s `ModelForm` provides a convenient way to create forms directly from models, reducing boilerplate code.

#### Step 1: Create a ModelForm

1. **Open `blog/forms.py`:**

   ```python
   from django import forms
   from .models import Post

   class PostForm(forms.ModelForm):
       class Meta:
           model = Post
           fields = ['title', 'content', 'image']
   ```

#### Step 2: Use the ModelForm in a View

1. **Open `blog/views.py`:**

   ```python
   from django.shortcuts import render, redirect
   from django.contrib.auth.decorators import login_required
   from .forms import PostForm

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

2. **Update the URL pattern in `blog/urls.py`:**

   ```python
   from django.urls import path
   from .views import blog_home, post_detail, create_post

   urlpatterns = [
       path('', blog_home, name='blog_home'),
       path('post/<int:post_id>/', post_detail, name='post_detail'),
       path('create/', create_post, name='create_post'),
   ]
   ```

### Customizing Form Fields and Validation

You can customize the form fields and add custom validation to your forms.

#### Step 3: Customize Form Fields

1. **Open `blog/forms.py`:**

   ```python
   from django import forms
   from .models import Post

   class PostForm(forms.ModelForm):
       class Meta:
           model = Post
           fields = ['title', 'content', 'image']
           widgets = {
               'title': forms.TextInput(attrs={'class': 'form-control', 'placeholder': 'Enter title'}),
               'content': forms.Textarea(attrs={'class': 'form-control', 'placeholder': 'Enter content'}),
           }
   ```

#### Step 4: Add Custom Validation

1. **Open `blog/forms.py`:**

   ```python
   from django import forms
   from .models import Post

   class PostForm(forms.ModelForm):
       class Meta:
           model = Post
           fields = ['title', 'content', 'image']

       def clean_title(self):
           title = self.cleaned_data.get('title')
           if 'django' not in title.lower():
               raise forms.ValidationError('Title must contain the word "django".')
           return title
   ```

### Handling Form Submission and Redirection

When a form is submitted, you need to handle the data and usually redirect the user to another page.

#### Step 5: Update the View to Handle Custom Validation

1. **Open `blog/views.py`:**

   ```python
   from django.shortcuts import render, redirect
   from .forms import PostForm

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

2. **Update the Template to Display Form Errors:**

   ```html
   <!-- blog/templates/blog/create_post.html -->
   <!DOCTYPE html>
   <html>
   <head>
       <title>Create Post</title>
   </head>
   <body>
       <h1>Create a New Blog Post</h1>
       <form method="post" enctype="multipart/form-data">
           {% csrf_token %}
           {{ form.as_p }}
           <button type="submit">Submit</button>
       </form>
   </body>
   </html>
   ```

### Assignment: Create and Customize a Comment Form

1. **Create a `CommentForm` in `blog/forms.py` with fields for `post`, `author`, and `content`.**
2. **Create a view in `blog/views.py` to handle the comment form submission.**
3. **Create a template named `create_comment.html` to display the comment form.**
4. **Add a URL pattern in `blog/urls.py` for the comment form view.**
5. **Customize the form fields and add validation to ensure the `content` field is not empty.**
6. **Handle form submission and redirect the user to the post detail page upon successful submission.**
7. **Test the comment form by navigating to the appropriate URL and submitting the form.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)