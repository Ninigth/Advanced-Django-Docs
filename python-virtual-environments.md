# Python Virtual Environments

Contributor: **ISA SAMIEZADE-YAZD**

AI-assisted review draft. Practice these commands and revise the explanations to reflect your understanding before submission.

## Purpose

A virtual environment keeps a project's installed packages separate from other projects. This lets two projects use different dependency versions. It uses an existing Python installation; it is not a virtual machine.

## Create and activate

Run from your individual project directory, not inside the environment folder.

Windows PowerShell:

```powershell
py -m venv djvenv
.\djvenv\Scripts\Activate.ps1
```

macOS or Linux bash/zsh:

```bash
python3 -m venv djvenv
source djvenv/bin/activate
```

Activation changes which interpreter `python` selects in that terminal.

## Verify and deactivate

```bash
python --version
python -c "import sys; print(sys.executable); print(sys.prefix != sys.base_prefix)"
python -m pip --version
```

Expect an interpreter path inside `djvenv`, `True`, and a pip location inside the environment.

```bash
deactivate
```

Deactivation restores the terminal's previous environment; it does not delete installed packages. Reactivate when returning to the project.

## Troubleshooting

If PowerShell blocks activation, use the environment interpreter directly:

```powershell
.\djvenv\Scripts\python.exe -m pip --version
```

If activation cannot find the file, check your current directory and whether creation succeeded. Recreate environments after moving projects instead of copying them. Add `djvenv/` to your project's `.gitignore`; keep source files outside that folder.

## Practice

Compare `sys.executable` before and after activation. Explain the difference using your own output.

## Resources and next section

- [Official Python venv documentation](https://docs.python.org/3/library/venv.html)
- [Python Packages and Dependencies](python-packages-dependencies.md)
- [Team documentation](README.md)

AI disclosure: AI assisted with this draft and command selection. Add your own verification and learning experience after practice.
