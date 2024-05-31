## Day 69: Testing in Django

### Introduction to Testing in Django

Testing is a crucial part of software development. It ensures that your application behaves as expected and helps catch bugs early. Django provides a robust testing framework that allows you to write unit tests and integration tests for your application.

### Setting Up Tests

In Django, tests are typically written in the `tests.py` file within each app. By default, Django includes a testing module that you can use to write your tests.

### Writing Basic Tests

Let's start by writing some basic tests for our blog application.

#### Step 1: Writing Tests for Models

1. **Open `blog/tests.py`:**

   ```python
   from django.test import TestCase
   from .models import Post

   class PostModelTest(TestCase):

       def setUp(self):
           Post.objects.create(title="Test Post", content="This is a test post content.")

       def test_post_content(self):
           post = Post.objects.get(id=1)
           expected_object_name = f'{post.title}'
           self.assertEqual(expected_object_name, 'Test Post')
           self.assertEqual(post.content, 'This is a test post content.')
   ```

   In this test, we create a `Post` instance in the `setUp` method, which is run before every test. We then test that the content of the `Post` instance is as expected.

#### Step 2: Running the Tests

To run the tests, use the `test` command:

```bash
python manage.py test
```

Django will discover and run all the tests in your project, and you will see the test results in the console.

### Writing Tests for Views

Let's write some tests to check the views.

1. **Open `blog/tests.py` and add the following code:**

   ```python
   from django.test import TestCase
   from django.urls import reverse
   from .models import Post

   class PostViewTest(TestCase):

       def setUp(self):
           self.post = Post.objects.create(title="Test Post", content="This is a test post content.")

       def test_view_url_exists_at_proper_location(self):
           response = self.client.get('/blog/')
           self.assertEqual(response.status_code, 200)

       def test_view_url_accessible_by_name(self):
           response = self.client.get(reverse('blog_home'))
           self.assertEqual(response.status_code, 200)

       def test_view_uses_correct_template(self):
           response = self.client.get(reverse('blog_home'))
           self.assertEqual(response.status_code, 200)
           self.assertTemplateUsed(response, 'blog/home.html')
   ```

   In these tests, we check if the URL exists and returns a status code of 200, if the URL is accessible by name, and if the correct template is used.

### Writing Tests for Forms

Next, let's write tests for our forms.

1. **Open `blog/tests.py` and add the following code:**

   ```python
   from .forms import PostForm

   class PostFormTest(TestCase):

       def test_post_form_valid(self):
           form = PostForm(data={'title': "Test Post", 'content': "This is a test post content."})
           self.assertTrue(form.is_valid())

       def test_post_form_invalid(self):
           form = PostForm(data={'title': "", 'content': "This is a test post content."})
           self.assertFalse(form.is_valid())
   ```

   In these tests, we check if the form is valid when given valid data and if it is invalid when given invalid data.

### Writing Tests for Authentication

Let's write tests for user registration and login.

1. **Open `blog/tests.py` and add the following code:**

   ```python
   from django.contrib.auth.models import User

   class UserAuthenticationTest(TestCase):

       def test_register_user(self):
           response = self.client.post(reverse('register'), {
               'username': 'testuser',
               'email': 'testuser@example.com',
               'password1': 'testpassword',
               'password2': 'testpassword'
           })
           self.assertEqual(response.status_code, 302)
           self.assertTrue(User.objects.filter(username='testuser').exists())

       def test_login_user(self):
           user = User.objects.create_user(username='testuser', password='testpassword')
           response = self.client.post(reverse('login'), {
               'username': 'testuser',
               'password': 'testpassword'
           })
           self.assertEqual(response.status_code, 302)
           self.assertTrue(response.wsgi_request.user.is_authenticated)
   ```

   In these tests, we check if a user can register and log in successfully.

### Assignment: Write and Run Tests

1. **Write tests for the `Comment` model.**
2. **Write tests for the `create_post` view, checking that only authenticated users can access it.**
3. **Write tests for the `PostForm`, ensuring that it handles file uploads correctly.**
4. **Run the tests and ensure all tests pass.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)