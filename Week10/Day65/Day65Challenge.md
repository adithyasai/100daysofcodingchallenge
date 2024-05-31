## Day 65: Static Files and Media Files

### Understanding Static Files and Media Files in Django

Static files are all the files that aren’t dynamic, like CSS, JavaScript, and images. Media files, on the other hand, are user-uploaded content like profile pictures, documents, etc. Django provides a way to manage both types of files easily.

### Managing Static Files

First, let’s learn how to handle static files in Django.

#### Step 1: Configure Static Files Settings

In `blogproject/settings.py`, add or update the following settings to configure static files:

```python
STATIC_URL = '/static/'
STATICFILES_DIRS = [
    BASE_DIR / "static",
]
```

#### Step 2: Create a Static Directory

Create a `static` directory at the root level of your project:

```
blogproject/
    static/
        css/
            styles.css
        js/
            scripts.js
        images/
            logo.png
```

#### Step 3: Use Static Files in Templates

Create a CSS file `styles.css` inside `static/css/`:

```css
/* static/css/styles.css */
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

Update the `base.html` template to include the CSS file:

```html
<!-- blog/templates/blog/base.html -->
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}My Blog{% endblock %}</title>
    <link rel="stylesheet" type="text/css" href="{% static 'css/styles.css' %}">
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

Ensure you load the static files in your template:

```html
{% load static %}
```

### Managing Media Files

Now, let’s handle media files for user-uploaded content.

#### Step 1: Configure Media Files Settings

In `blogproject/settings.py`, add or update the following settings to configure media files:

```python
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

#### Step 2: Update the Post Model

Update the `Post` model in `blog/models.py` to include an image field:

```python
from django.db import models

class Post(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    image = models.ImageField(upload_to='post_images/', null=True, blank=True)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.title
```

Run the migrations to apply the changes:

```bash
python manage.py makemigrations blog
python manage.py migrate
```

#### Step 3: Create a Form to Handle Media Files

Update the `PostForm` in `blog/forms.py` to handle file uploads:

```python
from django import forms
from .models import Post

class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = ['title', 'content', 'image']
```

#### Step 4: Update the View to Handle Media Files

Update the `create_post` view in `blog/views.py` to handle file uploads:

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

#### Step 5: Update the Template to Handle Media Files

Update the `create_post.html` template to include the file upload field:

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

#### Step 6: Serve Media Files During Development

During development, Django can serve media files using the `django.conf.urls.static` module. Update `blogproject/urls.py`:

```python
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('blog/', include('blog.urls')),
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

### Assignment: Implement Static and Media File Handling

1. **Create static files (CSS, JavaScript) and use them in your templates.**
2. **Update the `Post` model to include an image field for media uploads.**
3. **Update the `PostForm`, view, and template to handle media file uploads.**
4. **Run the server and test the functionality by creating posts with images and ensuring they display correctly.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)