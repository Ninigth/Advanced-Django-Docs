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

## .gitignore

The `.gitignore` file tells Git which files or folders should not be uploaded to Github.

For this project:
```text
djvenv/
__pycache/
.DS_Store
```

The `djvenv/` folder should not be uploaded because it's too large and is made for the local computer. Another developer can create their own virtual environment and install the needed packages using `requirements.txt`.

## Git and Github

Git tracks changes to files on the computer.

Github stores the Git repository online so it can be shared and accessed by other developers.

### Check Repository Status
```powershell
git status
```

### Add Files
```powershell
git add .
```

### Commit Files
```powershell
git push
```

## Common Problems and Troubleshooting

### Problem 1: PowerShell says Running Scripts Is Disabled

Example problem:
```text
running scripts is disabled on this system
```

Fix:
```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

Then activate the virtual environment again:
```powershell
.\djvenv\Scripts\Activate.ps1
```

### Problem 2: Django Is Not Found

If this command:
```powershell
python -m django --version
```

shows:
```text
No module named django
```

then Django is not installed in the active virtual environment.

Make sure `(djvenv)` appears in the terminal, then run:
```powershell
python -m pip install django
```

## Useful Commands

| Task | Command |
|---|---|
| Check Python version | `python --version` |
| Create virtual environment | `py -m venv djvenv` |
| Activate virtual environment | `.\djvenv\Scripts\Activate.ps1` |
| Install Django | `python -m pip install django` |
| Check Django version | `python -m django --version` |
| Create Django project | `django-admin startproject django_project .` |
| Start server | `python manage.py runserver` |
| Stop server | `Ctrl + C` |
| Deactivate environment | `deactivate` |
| List installed packages | `python -m pip freeze` |
| Create requirements.txt | `python -m pip freeze > requirements.txt` |
| Check Git status | `git status` |
| Add files to Git | `git add .` |
| Commit changes | `git commit -m "Set up Django development environment"` |
| Push to GitHub | `git push` |

## Reliable Resources

- [Django Documentation](https://docs.djangoproject.com/)
- [Django Installation FAQ](https://docs.djangoproject.com/en/stable/faq/install/)
- [Python Documentation](https://docs.python.org/)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com/)
