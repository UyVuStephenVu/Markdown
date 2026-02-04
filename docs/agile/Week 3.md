# Week 3 - Github, Jira

## I. Using git as a team (Review)

### 1. Repository Setup and Team Access

A team workflow starts with a shared repository. One team member creates the repository and configures the basics such as a README.md, .gitignore, and optional license. Team members are then added as collaborators with appropriate permissions.

Once invited, each developer clones the repository locally:

``` bash
git clone https://github.com/org-or-user/project-name.git
```

This creates a local copy that stays connected to the team’s shared codebase.

### 2. Branching Strategy and Local Development

To avoid conflicts and broken code, teams do not work directly on the main branch. Instead, each task or feature is developed in its own branch.

**A common approach:**

* main – stable, production-ready code (Never work directly on main)
* dev – integration branch (optional)
* feature/* – individual features or fixes

Creating and switching to a new branch:

``` bash
git checkout -b feature/login-form
```

Each branch represents one focused change, making collaboration safer and more organized.

### 3. Making Changes, Committing, and Pushing

As developers work, they regularly save progress using commits. Good commits are small, focused, and clearly described.

Typical workflow:

``` bash
git status
git add .
git commit -m "Add validation to login form"
```

💡 Tip: If a commit message needs “and”, it’s probably **doing too much**.

Once a feature is ready or needs review, the branch is pushed to GitHub:

``` bash
git push origin feature/login-form
```

At this point, the work is visible to the rest of the team.

### 4. Pull Requests and Code Reviews

Pull Requests (PRs) are the core of team collaboration on GitHub. A PR proposes merging a feature branch into main.

When creating a PR, developers explain:

* What was changed
* Why the change was made
* Any related issues

Team members review the code, leave comments, and suggest improvements. This process helps catch bugs early, maintain code quality, and share knowledge across the team.

Once approved, the PR is merged using the team’s preferred merge method (often squash and merge for a clean history).

### 5. Keeping Everyone in Sync and Handling Conflicts

Before starting work, developers pull the latest changes to avoid conflicts:

``` bash
git checkout main
git pull origin main
```

They then merge main into their feature branch:

``` bash
git checkout feature/login-form
git merge main
```

Merge conflicts can occur when multiple people edit the same code. These are resolved manually by choosing the correct changes, then committing the fix. Conflicts are a normal part of teamwork, not a mistake.

### 6. Using Issues for Task Tracking and Communication

GitHub Issues help teams manage work without relying on scattered messages. Issues are used to track bugs, features, and tasks, and can be assigned to specific team members.

Issues can also be linked directly to pull requests, creating a clear record of what problem each change addresses.

### 7. Documentation and Team Conventions

A well-maintained README.md acts as the team’s instruction manual. It typically includes:

* Project overview
* Setup and run instructions
* Branching rules
* Contribution guidelines

Clear documentation reduces onboarding time and prevents confusion as the project grows.


## II. **Github Commonly used commands**

1. Daily Workflow

``` bash
// Check repo status:
git status

// See commit history:
git log
git log --oneline

// Pull latest changes:
git pull

// Stage changes:
git add .
git add file.ts

// Commit changes:
git commit -m "Clear, meaningful message"

// Push your branch:
git push
```

2. **Branching**

``` bash
// List branches:
git branch


// Create and switch branch:
git checkout -b feature/login

// Switch branches:
git checkout main

// Delete branch (local):
git branch -d feature/login

// Delete branch (remote):
git push origin --delete feature/login
```

3. Syncing With the Team

``` bash
// Update main:
git checkout main
git pull origin main

// Merge main into your branch:
git checkout feature/login
git merge main

// Fetch without merging:
git fetch
```

4. Undoing Mistakes (Very Common)

``` bash
// Undo unstaged changes:
git checkout -- file.ts

// Unstage a file:
git reset file.ts

// Undo last commit (keep changes):
git reset --soft HEAD~1

// Undo last commit (discard changes):
git reset --hard HEAD~1
```

5. Handling Merge Conflicts

``` bash
// Check conflicted files:
git status

// After fixing conflicts:
git add .
git commit

// Abort a merge:
git merge --abort
```

6. Working With Remotes (GitHub)

``` bash
// View remotes:
git remote -v

// Add a remote:
git remote add origin https://github.com/user/repo.git

// Set upstream branch:
git push -u origin feature/login
```

## III. Using Jira with Github

### 1. What is Jira?

Jira is a project management and issue-tracking tool (Similar to Trello) used to organize and track work in software teams. While GitHub manages code changes and collaboration, Jira manages the work itself: what needs to be done, why it matters, and what stage it is in. Tasks, bugs, and features are created as Jira issues and move through a workflow such as “To Do,” “In Progress,” and “Done.”

Jira integrates with GitHub so development activity is automatically linked to planning. When branches, commits, or pull requests reference a Jira issue, that information appears directly on the issue. This connects high-level planning in Jira with low-level implementation in GitHub, giving teams clear visibility from task definition to completed code.

Jira also helps automate processes like cloning a repository or moving a task from doing to done.