---
title: Git
theme: blood  # beige, black, blood, league, moon, night, serif, simple, sky, solarized, white
highlightTheme: nord  # https://github.com/highlightjs/highlight.js/tree/main/src/styles
revealOptions:
  transition: none
---
<!-- .slide: data-background-color="#4287f5" -->

![](https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg)

---
### Agenda
- Useful commands
- Practical usage of git
- Exercises

---

### What is Git?
<!-- .slide: data-background="https://media.giphy.com/media/ZaJtnTY8tFZz0PvmW9/giphy.gif" data-background-opacity="0.7" -->
- Version control
  - Keep track of files over time
  - Revert back to a previous state
  - Compare changes

---

### Commands 🤓

A quick overview of some commands:

```bash
git pull      # from remote to local
git push      # to remote from local
git add       # stage changes to a commit
git commit    # commit staged changes
git checkout  # switch branch or create a new
git rebase    # rebase commits
git reset     # reset HEAD | optional --hard
git reflog    # view your reference logs
```
---

### Clone a repo

Clone the repository using https or ssh

```bash
# SSH
git clone git@github.com:<username>/<repository>.git

# HTTPS
git clone https://github.com/<username>/<repository>.git
```

---


### Write some awesome code

<!-- .slide: data-background="https://c.tenor.com/z4_HKSF6Nx8AAAAC/typing-jim-carrey.gif" data-background-opacity="0.4" -->

---

### Diff

*look at the improvements*

```bash
git diff
```

```diff
-const someList = [1, '2', 3, '4']
-for (x of something) {
-    console.log('how to javskript?', x)
-}
+some_list = [1, '2', 3, '4']
+for x in something:
+    print('python > javascript', x)
```
<!-- .slide: data-background="https://c.tenor.com/OWrqUWuNRHEAAAAC/thumbs-up-internet.gif" data-background-opacity="0.4" -->
<!-- 

---

### Commit
Record your changes to the repository
```bash
git add <item> or git add .    # stages your changes
git commit -m <commit message> # records the changes
```
Optional: Amend the commit

```bash
git commit --amend # if you did an oopsie
```

---

### Push

Push your new changes to the remote

```bash
git push origin <branch-name>
```
Optional: Force with lease
```bash
git push --force-with-lease origin <branch-name>
```

---

### Pull

Get new remote changes to your machine

```bash
git pull
```

<!-- .slide: data-background="https://c.tenor.com/6iq8JGtbYZ8AAAAd/cat-drag.gif" data-background-opacity="0.4" -->
---

### Branching

Jump to a branch or create a new one

Using feature-branches helps with scalability

```bash
git checkout <branch-name>    # checkout existing branch
git checkout -b <branch-name> # create a new branch
```
Optional: Tag the branch 

```bash
git checkout -b feature/<branch-name>
```
---


### Merge < Rebase*

Keep a maintainable commit history

```bash
git rebase development
```

> <img src="https://www.bitsnbites.eu/wp-content/uploads/2015/12/1-nonlinear-vs-linear.png" alt="linear vs. non-linear" width="400"/>

*personal taste

---


### Merge conflicts 💢

Conflicts will happen when multiple people work together

```diff
<<<<<<< HEAD (Current Change)
const someList = [1, '2', 3, '4']
for (x of something) {
    console.log('how to javskript?', x)
}
=======
some_list = [1, '2', 3, '4']
for x in something:
    print('python > javascript', x)
>>>>>>> (Incoming Changes)
```

---


### Reflog 📓
```bash
git reflog
git reset --hard <commit>
```
Good for CTRL - Z when you messed up locally.
---

### Exercise 1 👷
Linear history (to and from master)  
15 minutes

1. Create a repository from [template](https://github.com/AndreasPB/large-systems-template)
2. Clone the repository
4. Edit and commit the same lines (create a conflict)
3. Push and pull changes
5. Solve conflict

---

### Exercise 2 👷
Semi-linear (using feature branches)  
15 minutes

1. Checkout to a feature branch
2. Add, commit and push a feature
3. Review and merge feature on [GitHub](https://github.com)
