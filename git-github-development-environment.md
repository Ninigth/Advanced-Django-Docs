# Git and GitHub Development Environment

**By Hassan Moharrem**

## What is Git?

Git is a version control system.

It keeps track of changes made to files in a project. This allows developers to save different versions of their work and see what has changed over time.

Git works on the local computer.

For example, commands like these use Git:

```powershell
git status
git add .
git commit -m "Add Django framework and setup documentation"
```

## What is GitHub?

GitHub is an online service that stores Git repositories.

GitHub allows developers to:

- store projects online
- share projects with other people
- work with team members
- keep a backup of their code
- review changes made to a project

Git and GitHub work together, but they are not the same thing.

A simple way to remember the difference is:

```text
Git = tracks changes to files
GitHub = stores the Git repository online
```

## What is a Repository?

A repository, also called a repo, is a project folder that Git tracks.

A repository contains:

- project files
- folders
- code
- Git history
- information about changes made to the project

A repository can exist locally on a computer and remotely on GitHub.

## Creating a Local Git Repository

To turn a project folder into a Git repository, first open PowerShell and go into the project folder.

Then run:

```powershell
git init
```

This creates a local Git repository.

Git can now begin tracking changes inside the project.

## Checking the Repository

To check the current state of the repository, run:

```powershell
git status
```

This command can show:

- files that Git is not tracking yet
- files that have been changed
- files that are ready to be committed
- whether the local branch is ahead of or behind GitHub

For example:

```text
Untracked files:
    manage.py
    requirements.txt
```

means Git sees the files, but they have not been added yet.

## Adding Files to Git

Before making a commit, files must first be added.

To add all changed files in the current project, run:

```powershell
git add .
```

The period means to add all changes in the current folder.

After this, run:

```powershell
git status
```

again.

The files should now appear under:

```text
Changes to be committed:
```

## What is a Commit?

A commit saves a version of the project in Git.

A commit should include a short message that explains what was changed.

Example:

```powershell
git commit -m "Set up Django development environment"
```

Another example:

```powershell
git commit -m "Add Django framework and setup documentation"
```

A good commit message should briefly explain the work that was done.

## Basic Git Workflow

A common Git workflow is:

### 1. Check the repository

```powershell
git status
```

### 2. Add the changes

```powershell
git add .
```

### 3. Check the changes again

```powershell
git status
```

### 4. Commit the changes

```powershell
git commit -m "Describe what was changed"
```

### 5. Push the commit to GitHub

```powershell
git push
```

The basic process is:

```text
Edit files
    ↓
git status
    ↓
git add .
    ↓
git commit
    ↓
git push
    ↓
GitHub
```

## Connecting a Local Repository to GitHub

A local Git repository can be connected to a repository on GitHub.

The command looks like:

```powershell
git remote add origin <repository-url>
```

The repository URL is replaced with the actual GitHub repository address.

Example:

```powershell
git remote add origin https://github.com/username/project-name.git
```

## What is origin?

`origin` is the common name Git uses for the remote GitHub repository.

For example:

```powershell
git push origin main
```

means:

```text
Push the main branch to the GitHub repository called origin.
```

Once the connection is already set up, usually this command is enough:

```powershell
git push
```

## What is a Branch?

A branch is a separate line of work inside a Git repository.

The main branch is commonly called:

```text
main
```

The command:

```powershell
git branch -M main
```

sets the current branch name to `main`.

Branches allow developers to work on changes without always changing the main version of the project right away.

## Pushing to GitHub

After making a commit, the changes still exist only in the local Git repository until they are pushed.

To send the commits to GitHub, run:

```powershell
git push
```

The first push may use:

```powershell
git push -u origin main
```

After that, Git remembers which remote branch is connected, so normally this is enough:

```powershell
git push
```

## What is .gitignore?

The `.gitignore` file tells Git which files and folders should not be tracked.

For this Django project, the `.gitignore` file includes:

```text
djvenv/
__pycache__/
.DS_Store
```

## Why is djvenv Ignored?

The folder:

```text
djvenv/
```

contains the Python virtual environment.

It should not be uploaded to GitHub because:

- it contains many files
- it can take up unnecessary space
- it is made for the local computer
- another developer can create their own virtual environment

Instead of sharing the entire virtual environment, the project uses:

```text
requirements.txt
```

That file tells another developer which Python packages and versions the project needs.

## What is __pycache__?

The folder:

```text
__pycache__/
```

contains files Python creates automatically while running programs.

These files do not need to be shared because Python can create them again.

## What is .DS_Store?

The file:

```text
.DS_Store
```

is created by macOS to store folder display settings.

It is not part of the project code, so it does not need to be stored in GitHub.

## Files That Should Be Stored in GitHub

For this Django project, files that should be stored include:

```text
django_project/
manage.py
requirements.txt
.gitignore
```

These files are part of the project and help another developer understand or run it.

## Files That Should Not Be Stored in GitHub

The virtual environment should not be stored:

```text
djvenv/
```

Files that are created automatically and are not needed should also usually be ignored, such as:

```text
__pycache__/
.DS_Store
```

## requirements.txt and GitHub

The file:

```text
requirements.txt
```

contains a list of the Python packages the project needs and their versions.

It can be created with:

```powershell
python -m pip freeze > requirements.txt
```

Another developer who clones the project will not receive the `djvenv` folder.

Instead, they can use `requirements.txt` to install the packages needed by the project.

## What Does Clone Mean?

Cloning means downloading a copy of a Git repository from GitHub onto a computer.

A developer can clone a repository and then work with the project locally.

The basic idea is:

```text
GitHub repository
        ↓
      clone
        ↓
Developer's computer
```

## Why Version Control is Useful

Version control helps developers keep track of their work.

Git makes it possible to:

- see which files changed
- save versions of a project
- write notes about each saved version
- share changes with a team
- keep code stored online through GitHub

This is especially useful when more than one person is working on the same project.

## Working With a Team Repository

For the team technical documentation, all team members contribute to a shared GitHub repository.

Each person can work on their assigned Markdown documentation and add their changes to the repository.

The team repository allows everyone to contribute their own section while keeping the documentation together in one place.

The assignment also uses GitHub Pages to publish the team's Markdown documentation as a website.

## Markdown Files in GitHub

Markdown files use the file extension:

```text
.md
```

Example:

```text
django-framework-setup.md
git-github-development-environment.md
```

Markdown lets developers create headings, lists, links, tables, and code blocks using plain text.

Example:

```markdown
# Main Heading

## Smaller Heading

- Item one
- Item two

**Bold text**

`git status`
```

## Common Git Commands

| Task | Command |
|---|---|
| Create a Git repository | `git init` |
| Check repository status | `git status` |
| Add all changes | `git add .` |
| Commit changes | `git commit -m "message"` |
| Rename branch to main | `git branch -M main` |
| Connect to GitHub | `git remote add origin <repository-url>` |
| Push first time | `git push -u origin main` |
| Push later changes | `git push` |

## Example Full Workflow

After editing project files:

```powershell
git status
```

Then add the changes:

```powershell
git add .
```

Check them again:

```powershell
git status
```

Commit the changes:

```powershell
git commit -m "Update project documentation"
```

Push them to GitHub:

```powershell
git push
```

## Common Problems and Troubleshooting

### Problem 1: Files Do Not Appear on GitHub

If changes were made locally but do not appear on GitHub, they may not have been pushed yet.

Check:

```powershell
git status
```

If the terminal says the branch is ahead of `origin/main`, run:

```powershell
git push
```

### Problem 2: A File Is Not Being Tracked

Use:

```powershell
git status
```

If the file appears under:

```text
Untracked files
```

add it with:

```powershell
git add .
```

Then commit it:

```powershell
git commit -m "Add new files"
```

### Problem 3: djvenv Appears in Git Status

If the `djvenv` folder appears in `git status`, check the `.gitignore` file.

It should contain:

```text
djvenv/
```

The virtual environment should not be uploaded to GitHub.

### Problem 4: Local Changes Have Not Been Saved to Git

Editing and saving a file in VS Code does not automatically create a Git commit.

You still need to run:

```powershell
git add .
```

and:

```powershell
git commit -m "Describe the change"
```

Then push the commit:

```powershell
git push
```

## Git vs GitHub Summary

| Git | GitHub |
|---|---|
| Runs on the computer | Runs online |
| Tracks file changes | Stores Git repositories |
| Creates commits | Stores pushed commits |
| Works without internet | Usually requires internet |
| Uses commands like `git status` and `git commit` | Lets developers view and share repositories online |

## Reliable Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com/)
- [GitHub Git Guide](https://github.com/git-guides)
