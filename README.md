# Git Lab 2 Documentation

## Overview

This lab demonstrates the basic workflow of Git including repository initialization, working with branches, merging changes, managing remote repositories, and using tags.

The lab also covers switching branches without committing changes and adding images inside a README file.

---

## Table of Contents

1. Initialize Local Repository
2. Connect Repository to GitHub
3. Create and Push Branches
4. Merge Branches into Main
5. Delete Branches
6. Checkout Branch Without Committing Changes
7. Create Annotated Tag
8. Push Tag to Remote Repository
9. List Tags
10. Delete Tag
11. Add Image to README
12. Tell Me Section

---

## 1. Initialize Local Repository

Create a project directory and initialize a Git repository.

```bash
mkdir lab2
cd lab2
git init
```

Create the README file.

```bash
touch README.md
```

Add the file to the staging area.

```bash
git add README.md
```

Commit the file to the repository.

```bash
git commit -m "initial commit"
```

---

## 2. Connect Repository to GitHub

Add the remote repository.

```bash
git remote add origin https://github.com/USERNAME/git-lab2.git
```

Rename the default branch to main.

```bash
git branch -M main
```

Push the repository to GitHub.

```bash
git push -u origin main
```

The `-u` option sets the upstream branch so future push commands can be executed with `git push` only.

---

## 3. Create and Push Branches

### Create dev branch

```bash
git checkout -b dev
```

Create a file inside the dev branch.

```bash
touch dev.txt
```

Add and commit the file.

```bash
git add dev.txt
git commit -m "add dev file"
```

Push the branch to the remote repository.

```bash
git push origin dev
```

---

### Create test branch

Return to the main branch.

```bash
git checkout main
```

Create a new branch called test.

```bash
git checkout -b test
```

Create a file inside the branch.

```bash
touch test.txt
```

Add and commit the file.

```bash
git add test.txt
git commit -m "add test file"
```

Push the test branch.

```bash
git push origin test
```

---

## 4. Merge Branches into Main

Switch to the main branch.

```bash
git checkout main
```

Merge dev branch.

```bash
git merge dev
```

Merge test branch.

```bash
git merge test
```

Push the updated main branch.

```bash
git push origin main
```

---

## 5. Delete Branches

Delete branches locally.

```bash
git branch -d dev
git branch -d test
```

Delete branches from the remote repository.

```bash
git push origin --delete dev
git push origin --delete test
```

---

## 6. Checkout Branch Without Committing Changes

Sometimes we need to switch branches without committing the current changes.

Git provides the stash feature to temporarily store uncommitted changes.

Save current changes.

```bash
git stash
```

Switch branch.

```bash
git checkout branch-name
```

Restore the saved changes.

```bash
git stash pop
```

---

## 7. Create Annotated Tag

Create an annotated tag for a specific version.

```bash
git tag -a v1.7 -m "version 1.7 release"
```

Annotated tags contain additional information such as tagger name, date, and message.

---

## 8. Push Tag to Remote Repository

Push a specific tag.

```bash
git push origin v1.7
```

Push all tags.

```bash
git push --tags
```

---

## 9. List Tags

Display all tags in the repository.

```bash
git tag
```

Display detailed information about a specific tag.

```bash
git show v1.7
```

---

## 10. Delete Tag

Delete tag locally.

```bash
git tag -d v1.7
```

Delete tag from the remote repository.

```bash
git push origin --delete v1.7
```

---

## 11. Add Image to README

Images can be added to a README file using Markdown syntax.

Example:

```
![Project Image](image-url)
```

Example used in this repository:

```
![Project Image](https://pub-a0fe29ed512a454eb858af73b205c8eb.r2.dev/storage/thumbs/54/thumb1037.jpg)
```

---

## 12. Tell Me Section

### What is the staging area

The staging area is an intermediate step between the working directory and the repository.
Files are first added to the staging area using `git add` before being committed using `git commit`.

---

### Difference between local branch and remote branch

Local branches exist only on the developer's machine, while remote branches exist on the remote repository such as GitHub.
Local branches can be pushed to the remote repository using the `git push` command.

---

### What is a merge operation

Merge is the process of integrating changes from one branch into another.
It combines the histories of the branches and creates a new commit representing the merged state.

---

### What is an annotated tag

An annotated tag is a full object in the Git database that stores metadata such as the tagger name, email, date, and message.
Annotated tags are recommended when marking release versions of a project.

---

### What is git stash

Git stash temporarily saves uncommitted changes so the developer can switch branches without committing the work.
The changes can later be restored using `git stash pop`.

![Horse](https://pub-a0fe29ed512a454eb858af73b205c8eb.r2.dev/storage/thumbs/54/thumb1037.jpg)
