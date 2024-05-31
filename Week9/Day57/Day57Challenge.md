## Day 57: Setting Up Django

### Introduction to Django

Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design. It’s built by experienced developers and takes care of much of the hassle of web development, so you can focus on writing your app without needing to reinvent the wheel. Django is free and open source.

### Setting Up Your Environment

Before starting with Django, we need to set up our development environment. This involves installing Python, setting up a virtual environment, and installing Django.

### Installing Python

First, ensure that you have Python installed on your system. You can download and install Python from [python.org](https://www.python.org/downloads/).

### Setting Up a Virtual Environment

A virtual environment is a tool that helps to keep dependencies required by different projects in separate places. This is especially useful when working on multiple projects that require different versions of the same packages.

1. **Create a Virtual Environment:**

   ```bash
   python -m venv myenv
   ```

2. **Activate the Virtual Environment:**

   - On Windows:
     ```bash
     myenv\Scripts\activate
     ```
   - On MacOS/Linux:
     ```bash
     source myenv/bin/activate
     ```

### Installing Django

With your virtual environment activated, you can install Django using pip, which is the package installer for Python.

```bash
pip install django
```

### Creating Your First Django Project

Now that Django is installed, you can create your first project. Open your terminal or command prompt and run the following command:

```bash
django-admin startproject myproject
```

This will create a new directory called `myproject` with the following structure:

```
myproject/
    manage.py
    myproject/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```

### Running the Development Server

Navigate into your project directory and start the development server:

```bash
cd myproject
python manage.py runserver
```

You should see output indicating that the server is running. Open your web browser and go to `http://127.0.0.1:8000/`. You should see the Django welcome page, confirming that your setup is successful.

### Assignment: Create a Simple Django Project

1. **Set up a new virtual environment.**
2. **Install Django in the virtual environment.**
3. **Create a new Django project called `myblog`.**
4. **Run the development server and ensure that the Django welcome page is displayed.**

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)