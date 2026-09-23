# Django Framework and Setup

**By Hassan Moharrem**

## What is Django?

Django is a web framework made with Python. It gives developers a tool to build a website without starting from scratch.

## What is a Software Framework

A software framework is the foundation or "skeleton" that gives developers the tools to build more efficiently.
For example, Django created multiple files and folders automatically when I created my project.

```powershell
django-admin startproject django_project .
```

This saves considerable time because Django handles much of the basic setup for the project.

## Python and Django Version Compatibility

Before installing Django, it's important to make sure that the Python version and Django version are working together.

For this project:

- Python version: `3.14.7`
- Django version: `6.1.1`
- Compatible?: Yes

I checked the Django documentation to verify their compatibility.

## Check the Python Version

```powershell
python --version
```

Example result:
```text
Python 3.14.7
```

## Check the Django Version

```powershell
python -m django --version
```

Example result:
```text
6.1.1
```

## Virtual Environment

A virtual environment keeps the Python tools and packages for one project separate from other projects.

For this project, the virtual environment is called:
```text
djvenv
```

### Create the Virtual Environment

Make sure Powershell is inside the project folder, then run:

```powershell
py -m venv djvenv
```

### Activate the Virtual Environment

On Windows Powershell:

```powershell
.\djvenv\Scripts\Activate.ps1
```

When it's active, the terminal should show:
```text
(djvenv)
```
at the beginning of the command line.

### If PowerShell Blocks the Script

PowerShell may show an error saying that running scripts is disabled.

Run:
```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

Then activate the virtual environment again:
```powershell
.\djvenv\Scripts\Activate.ps1
```

The `Process` setting only applies to the current PowerShell window.

### Deactivate the Virtual Environment

When finished working, run:
```powershell
deactivate
```

## Install Django

Make sure the virtual environment is active before installing Django.

Run:
```powershell
python -m pip install django
```

Then verify that Django is installed:
```powershell
python -m django --version
```

If a version number appears, that means Django is available in the project's virtual environment.

## Create the Django Project

Make sure:
- the virtual environment is active
- PowerShell is inside the project folder

Then run:
```powershell
django-admin startproject django_project .
```

The period `.` at the end is necessary. This tells Django to create the project in the current folder.

After running the command, the project contains files similar to:
```text
django-portfolio/
│
├── django_project/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── djvenv/
├── manage.py
└── .gitignore
```

## Run the Django Development Server

Django includes a development server that lets you run the project on your own computer.

Start the server with:
```powershell
python manage.py runserver
```

The terminal should show an address similar to:
```text
https://127.0.0.1:8000/
```

Open that address in a web browser.
If Django is working correctly, the browser should show the Django success page.

## Stop the Development Server

To stop the server, return to PowerShell and press:
```text
Ctrl+C
```

## Start the Project Again Later

When returning to the project later:

### 1. Go to the project folder

```powershell
cd "C:\Users\...\Github\cd django-portfolio
```

### 2. Activate the virutal environment

```powershell
.\djvenv\Scripts\Activate.ps1
```

### 3. Start the Django Server

```powershell
python manage.py runserver
```

### 4. Open the site

```text
http://127.0.0.1:8000
```

## Python Packages and requirements.txt

The file `requirements.txt` contains the Python packages that the project needs and their versions.

To see the installed packages, run:
```powershell
python -m pip freeze
```

To create `requirements.txt`, run:
```powershell
python -m pip freeze > requirements.txt
```

Another developer can use the same file to install the same packages instead of receiving the virtual environment folder.
