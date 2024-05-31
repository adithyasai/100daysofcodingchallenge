## Day 61: Models and Databases

### Introduction to Django Models

Django models are the heart of the framework's database functionality. A model is a Python class that represents a database table, and each attribute of the class is a field of the table. Django models provide an abstraction layer, allowing you to work with databases using Python code instead of writing raw SQL queries.

### Creating and Migrating Models

In this session, we will create a model for our blog application and migrate it to the database.

#### Step 1: Define a Model

Open `blog/models.py` and define a `Post` model:

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

#### Step 2: Register the Model in Admin

To manage your model through the Django admin interface, you need to register it. Open `blog/admin.py` and register the `Post` model:

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

#### Step 3: Create and Apply Migrations

Django uses migrations to apply changes to the database schema. Generate the migration file and apply it to create the `Post` table in the database.

```bash
python manage.py makemigrations blog
python manage.py migrate
```

### Understanding Django ORM (Object-Relational Mapping)

Django ORM allows you to interact with the database using Python code. You can create, read, update, and delete records without writing SQL queries.

#### Step 4: Create and Query Model Instances

Open the Django shell to interact with the database:

```bash
python manage.py shell
```

In the shell, create and query `Post` instances:

```python
from blog.models import Post

# Create a new post
post = Post(title='First Post', content='This is the content of the first post.')
post.save()

# Query all posts
all_posts = Post.objects.all()
print(all_posts)

# Query a single post
first_post = Post.objects.get(id=1)
print(first_post)

# Update a post
first_post.title = 'Updated First Post'
first_post.save()

# Delete a post
first_post.delete()
```

### Using the Django Admin Interface

The Django admin interface is a powerful tool for managing your database models. It provides a user-friendly interface to add, edit, and delete records.

#### Step 5: Access the Admin Interface

1. **Create a Superuser:**

   ```bash
   python manage.py createsuperuser
   ```

   Follow the prompts to create an admin user.

2. **Run the Server:**

   ```bash
   python manage.py runserver
   ```

3. **Access the Admin Interface:**

   Open your web browser and navigate to `http://127.0.0.1:8000/admin/`. Log in with the superuser credentials you created. You should see the `Post` model registered under the `Blog` section.

### Assignment: Create and Manage Blog Posts

1. **Define a new model `Comment` in `blog/models.py` with fields for `post`, `author`, `content`, and `created_at`.**
2. **Register the `Comment` model in `blog/admin.py`.**
3. **Generate and apply migrations to create the `Comment` table in the database.**
4. **Use the Django admin interface to add, edit, and delete `Post` and `Comment` records.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)