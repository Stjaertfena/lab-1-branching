# Lab 1 - Branching & Merging

## Purpose & Goal
- Get comfortable working with branches
- Understand how the two main options (`merge` vs `rebase`) for integrating changes between branches works
- Understand how conflict resolution works

## Expectations
- Work in pairs
- For actions/operations performed on one computer – pair program!

## The assignment
### Step 1.1 - init repo
1. Create a new repository and publish it on GitHub
1. Invite your classmate as collaborator
1. Make sure both of you have managed to clone the repo onto your respective computers

### Step 1.2 - set baseline
1. Create a new branch and call it `develop`
1. Add the entire [src/](./src) folder (without modifying it) to the root of your project, `commit` and `push`
1. Verify that both of you have the latest code by pulling the `develop` branch, and that you can view [src/index.html](./src/index.html) in your browser.

### Step 1.3 - create own branches
1. From the tip of `develop` **create one branch each on your respective computers** (make sure to not give them the same name).
```
E.g.
$ git switch --create=my-cool-feature develop
```
1. `Push` your newly created branches and update your local repos with `fetch`.
```
$ git push --set-upstream origin my-cool-feature
$ git fetch
```
1. Verify that you are able to see each others branches in your local repository (using for example `gitk`)

### Step 1.4 - create divergent history
1. **_Dev-1_**: Modify the text inside the `<p>` tag in [index.html](./index.html), e.g. change it from _"Hello World!"_ to _"Hello Earth!"_; `commit` the change to your local branch and then `push` it to remote.
1. **_Dev-2_**: Modify the same `<p>` tag (but on your own branch) by adding the following css class `class="green"` to it; `commit` the change to your local branch and then `push` it to remote.
1. `Fetch` each others changes, your history should resemble this: INSERT IMAGE

### Step 1.5 - integrate changes (merge)
1. **_Dev-1_**: Checkout **_Dev-2's_** branch so you have a local reference to the two branches.
1. **_Dev-1_**: `Merge` the two branches together and resolve any potential conflicts
1. **_Dev-1_**: `Push` the merge commit to remote
1. **_Dev-2_**: `Pull` the changes so both of you have it locally

Congratulations, you have now completed the first part!

---

### Step 2.1 - integrate changes (rebase)
With the recent `merge` process completed, let's redo the same integration using `rebase` instead!
1. **_Dev-1_**: Create a new branch from the commit just before the merge, for example using:
```
$ git switch -c cool-feature HEAD~1
```
1. x
