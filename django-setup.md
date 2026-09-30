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

The original contributor recorded these versions; verify your own environment rather than treating them as a new installation check:

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
http://127.0.0.1:8000/
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
Set-Location "$env:USERPROFILE\django-portfolio"
```

### 2. Activate the virtual environment

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

The `.gitignore` file excludes matching untracked files from normal staging. It does not remove files already tracked by Git.

For this project:
```text
djvenv/
__pycache__/
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
git commit -m "Set up Django project"
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

## Project structure and request flow

Additional guidance and corrections by **ISA SAMIEZADE-YAZD**.

| File | Purpose |
| --- | --- |
| `manage.py` | Runs project commands such as checks and the development server |
| `settings.py` | Configures installed apps, database connections, and other settings |
| `urls.py` | Maps requested paths to views |
| `__init__.py` | Marks the directory as a Python package |
| `asgi.py` and `wsgi.py` | Provide entry points for compatible application servers |

A project combines configuration and apps. An app implements a feature, such as a portfolio or blog. Django supplies reusable structure so each project does not have to build request handling and configuration from scratch.

The browser is the client. It requests a URL; Django handles the request and returns a response. `localhost` refers to the same computer, and `127.0.0.1` is an IPv4 loopback address. A rendered page plus a successful request in the server log provides evidence of a response. GitHub Pages serves static files and cannot run the Django Python server.

## Check setup and troubleshoot

Run in the directory containing `manage.py`, with the environment active:

```bash
python manage.py check
python manage.py migrate
python manage.py runserver
```

`migrate` applies database migrations; commit application migration source files with the project. The development server is for local development, not public production hosting. If port 8000 is busy, stop your previous server or try `python manage.py runserver 8001` and open port 8001. If `manage.py` is missing, check your current folder before generating another project. Avoid names such as `django.py` that can shadow installed modules.

On macOS/Linux create the environment with `python3 -m venv djvenv` and activate with `source djvenv/bin/activate`. After activation the `python -m ...` commands are the same. For a file encoding-safe requirements export on Windows, see [packages and dependencies](python-packages-dependencies.md).

Check compatibility against the documentation for the actual installed Django version. The original 6.1.1 example is not a claim that every reader has installed it.

Sources: [Django tutorial](https://docs.djangoproject.com/en/6.0/intro/tutorial01/), [Django installation FAQ](https://docs.djangoproject.com/en/6.1/faq/install/).

[Back to documentation](README.md)
