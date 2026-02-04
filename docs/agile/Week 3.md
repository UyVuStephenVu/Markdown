# Week 3 - Starting sprint

## I. Using git as a team

### 1. Setting Up the Repository (One-Time)
**Create the repository**

One team member (usually the lead) should:

1. Create a new repository on GitHub
2. Choose Public or Private
3. Add:

    * README.md
    * .gitignore (for your language)
    * License (optional)

**Add team members**

1. Go to Settings → Collaborators
2. Invite teammates by GitHub username or email
3. Assign appropriate permissions:

    * Write – most developers
    * Admin – team lead

### 2. Cloning the Project Locally

Each team member clones the repo once:

``` bash
git clone https://github.com/org-or-user/project-name.git
cd project-name
```

This creates a local copy linked to the shared repository.

3. Branching: How Teams Avoid Chaos

Rule of thumb:
👉 Never work directly on main.

Common branch strategy

main – stable, production-ready code

dev – integration branch (optional)

feature/* – individual work

Example:

git checkout -b feature/login-form


Each feature, bug fix, or experiment gets its own branch.

4. Making Changes and Committing Properly
Make small, focused commits

Bad:

"fixed stuff"


Good:

"Add validation to login form"


Command flow:

git status
git add .
git commit -m "Describe what you changed"


💡 Tip: If a commit message needs “and”, it’s probably doing too much.

5. Pushing Work to GitHub

Push your branch (not main):

git push origin feature/login-form


The branch now exists on GitHub for the team to see.

6. Pull Requests (The Core of Teamwork)

A Pull Request (PR) is how code gets reviewed and merged.

Creating a PR

Go to the repo on GitHub

Click Compare & pull request

Fill in:

What you changed

Why you changed it

Any issues it fixes

Why PRs matter

Catch bugs early

Share knowledge

Keep main stable

Create a paper trail of decisions

7. Code Reviews: How Teams Review Code

Teammates should:

Read the code

Leave comments

Ask questions

Suggest improvements

Common review checks:

Does this break anything?

Is the code readable?

Does it follow team conventions?

Are there tests (if applicable)?

Once approved, the PR can be merged.

8. Merging Without Breaking Everything

Preferred merge option:

Squash and merge (clean history)

or Merge commit (keeps full history)

🚫 Avoid force-pushing to shared branches.

9. Staying in Sync With the Team

Before starting work each day:

git checkout main
git pull origin main


Then update your feature branch:

git checkout feature/login-form
git merge main


This prevents painful merge conflicts later.

10. Handling Merge Conflicts (It Happens)

When Git can’t auto-merge:

Open conflicted files

Choose correct code manually

Remove conflict markers (<<<<, ====, >>>>)

Commit the fix

Conflicts are normal — not a failure.

11. Using Issues for Team Communication

GitHub Issues replace messy chat messages.

Use issues to:

Track bugs

Assign tasks

Discuss features

Example issue:

Title: Login button not responsive
Assigned to: Alex
Labels: bug, frontend


Issues can be linked to PRs for full traceability.

12. README: Your Team’s Instruction Manual

A good team README includes:

Project description

Setup instructions

How to run the project

Branching rules

Contribution guidelines

This saves hours of onboarding time.

13. Best Practices for Team GitHub Use

✔ Commit often
✔ Pull before you push
✔ One feature per branch
✔ Review code you didn’t write
✔ Communicate via issues and PRs

❌ Don’t work on main
❌ Don’t push broken code
❌ Don’t ignore merge conflicts

Conclusion

Using GitHub as a team is less about commands and more about discipline and communication. Branches protect the codebase, pull requests protect quality, and issues protect clarity. When everyone follows the same workflow, GitHub becomes a powerful collaboration tool instead of a source of stress.

## II. Using Jira with Github