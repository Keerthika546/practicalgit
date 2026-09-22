# Learning Git & GitHub — Version Control Basics

**Git** is the version control tool; **GitHub** is the online platform that hosts your Git repositories.

`git status` shows which files in your working folder (e.g. `practicalgit`) have changes that haven't yet been staged or committed to your local repository (the hidden `.git` folder).

## Steps to Clone a GitHub Repo to Your System

1. Create or open a folder with any name.
2. Right-click inside the folder → **Open Terminal**.
3. Run `code .` to open the folder in VS Code.
4. In VS Code's terminal (not the code editor area), run: git clone <paste-the-link>

   You'll find this link on your GitHub repo page under the green **Code** button.

## Understanding the Hidden `.git` Folder

When you clone (or initialize) a repo, Git creates a hidden `.git` folder inside your working folder. This is your **local repository** — it tracks the full history of your project. The files and folders you see in your working folder are your actual working copies; the `.git` folder stores their tracked versions and history behind the scenes.

## Making and Saving Changes

5. Create or modify files in your working folder as needed.
6. Run `git add .` to **stage** your changes — this tells Git which changes you want to include in the next commit (it doesn't move anything into `.git` permanently yet, just marks it as ready).
7. Run `git status` again to confirm your changes are staged (shown in green, usually under *"Changes to be committed"*).
8. Run `git commit -m "commit message"` to save the staged changes into your local repository (`.git` folder) with a message describing what changed. This is similar to hitting "commit" in a GUI tool.
9. Run `git push origin main` to upload your committed changes to GitHub. Once pushed, your changes — and who made them — become visible on your repo's GitHub page.

## Why `git add` Is Needed — A Simple Example

Working folder files are the "live" files you actually edit. But Git doesn't automatically track every change as history — it needs you to explicitly say *"this is the version I want you to remember."* That's what `git add` does: it takes a snapshot of your files and puts it in the **staging area** — a middle step before the permanent `.git` history.

**Example:** Say you have a folder `myproject` with two files: `notes.txt` and `todo.txt`.

1. You edit both files.
2. Run `git status`
Changes not staged for commit:
modified: notes.txt
modified: todo.txt

   Both are changed, but nothing is staged yet.

3. You only want to save `notes.txt` right now (maybe `todo.txt` isn't ready). Run: git add notes.txt

4. Run `git status` again:
Changes to be committed:
modified: notes.txt

Changes not staged for commit:
modified: todo.txt

   `notes.txt` is staged and ready. `todo.txt` is still just sitting there, changed but untouched.

5. Run:git commit -m "Updated notes"

   Only `notes.txt` is saved into history. `todo.txt` stays uncommitted — you can finish and commit it separately later.

### The Three States

| Location | What It Means |
|---|---|
| **Working folder** | Your real, editable files — current state |
| **Staging area** (after `git add`) | A snapshot you've chosen to include in the next commit |
| **Local repo / `.git`** (after `git commit`) | Permanently saved history |

Staging lets you pick exactly which changes go into each commit — like packing a suitcase before shipping it, instead of being forced to save everything that's currently different.
small changes to see in the local - line updated in the github page directly
