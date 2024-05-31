## Day 70: Review and Practice

### Reviewing Key Concepts

Today, we will review the key concepts covered over the past two weeks. This review will help reinforce your understanding and ensure you are comfortable with the basics of Django before moving on to more advanced topics.

### Review Topics

1. **Django Project Structure**
   - Understanding the project and app structure.
   - Key files: `settings.py`, `urls.py`, `views.py`, `models.py`.

2. **Creating and Managing Models**
   - Defining models and fields.
   - Running migrations to create database tables.
   - Using the Django ORM to interact with the database.

3. **Working with Views and Templates**
   - Creating views and mapping them to URLs.
   - Using templates to render HTML content.
   - Template inheritance and static files.

4. **Forms in Django**
   - Creating and handling forms.
   - Using `ModelForm` to create forms from models.
   - Customizing form fields and validation.

5. **User Authentication**
   - Implementing user registration, login, and logout.
   - Restricting access to views using the `login_required` decorator.
   - Extending user models with profiles.

6. **Django Admin Interface**
   - Registering models in the admin interface.
   - Customizing the admin interface.
   - Using inline models for related data.

7. **Static and Media Files**
   - Managing static files (CSS, JavaScript, images).
   - Handling media files (user uploads).
   - Configuring static and media settings.

8. **Testing in Django**
   - Writing tests for models, views, and forms.
   - Running tests and interpreting results.
   - Ensuring code quality with automated tests.

### Practice Exercises

To solidify your understanding, complete the following practice exercises.

#### Exercise 1: Extend the Blog Application

1. **Add Categories to Posts:**
   - Create a `Category` model.
   - Modify the `Post` model to include a category field.
   - Update the views, templates, and forms to handle categories.

2. **Create a Comment Form:**
   - Create a `CommentForm` for submitting comments.
   - Update the `post_detail` view to handle comment submissions.
   - Display comments below each post in the template.

3. **User Profile Page:**
   - Create a profile page for users.
   - Allow users to update their profile information and upload a profile picture.
   - Display user profile information on their profile page.

#### Exercise 2: Build a Simple To-Do List Application

1. **Set Up the Project:**
   - Create a new Django project called `todolist`.
   - Create an app called `tasks`.

2. **Create Models:**
   - Define a `Task` model with fields for `title`, `description`, `completed`, and `due_date`.
   - Run migrations to create the database tables.

3. **Create Views and Templates:**
   - Create views for listing tasks, adding a new task, and marking a task as completed.
   - Create templates for each view, including a form for adding new tasks.

4. **User Authentication:**
   - Implement user registration, login, and logout.
   - Restrict access to task management views so that only authenticated users can manage their tasks.

5. **Testing:**
   - Write tests for the `Task` model, views, and forms.
   - Run the tests to ensure the application works as expected.

### Additional Practice Resources

- **Django Official Documentation:** [docs.djangoproject.com](https://docs.djangoproject.com/)
- **Django for Beginners Book:** A step-by-step guide to building web applications with Django.

### Assignment: Complete the Exercises

1. **Extend the blog application with categories, comment form, and user profile page.**
2. **Build a simple to-do list application with user authentication and task management.**
3. **Write and run tests for the new features and ensure all tests pass.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)