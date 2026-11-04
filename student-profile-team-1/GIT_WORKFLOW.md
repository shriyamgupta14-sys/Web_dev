# Git Workflow – Solutions for Every Worksheet Step

Commands follow the Bosscoder *Git Commands – Student Guide*. Replace `<team-number>`, `<owner>` and `<URL>` with your own values.

## One-time setup (every student)

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Step 1 – Create the public repository (Team Lead)

On GitHub: **New repository** → name `student-profile-team-<team-number>` → **Public**.

## Step 2 – Add README.md and invite collaborators (Team Lead)

```bash
mkdir student-profile-team-<team-number>
cd student-profile-team-<team-number>
git init
echo "# Student Profile Team <team-number>" > README.md
git status
git add .
git commit -m "Initial commit: add README"
git branch -M main
git remote add origin <URL>
git remote -v
git push -u origin main
```

Then on GitHub: **Settings → Collaborators → Add people** and invite every team member.

## Step 3 – Clone the repository (every member)

```bash
git clone <URL>
cd student-profile-team-<team-number>
git branch
```

## Step 4 – Create feature branch and HTML file (each developer)

**Student 2 – Profile Developer**
```bash
git switch -c feature/profile
# create profile.html
```

**Student 3 – Skills Developer**
```bash
git switch -c feature/skills
# create skills.html
```

**Student 4 – Contact Developer**
```bash
git switch -c feature/contact
# create contact.html
```

## Step 5 – Add, commit and push (each developer)

**Student 2**
```bash
git status
git add profile.html
git commit -m "Add profile page"
git push -u origin feature/profile
```

**Student 3**
```bash
git status
git add skills.html
git commit -m "Add skills page"
git push -u origin feature/skills
```

**Student 4**
```bash
git status
git add contact.html
git commit -m "Add contact page"
git push -u origin feature/contact
```

## Step 6 – Raise a Pull Request (each developer)

On GitHub, open the repository → **Compare & pull request** (or **Pull requests → New pull request**):

- base: `main`
- compare: your feature branch (`feature/profile`, `feature/skills` or `feature/contact`)
- Add a title and a short description, then click **Create pull request**.

## Step 7 – Review and merge (Team Lead)

On GitHub: **Pull requests →** open each PR → **Files changed** → **Review changes → Approve** → **Merge pull request → Confirm merge**.

## Step 8 – Verify all files are in main

```bash
git switch main
git pull origin main
git log --oneline
ls
```

`profile.html`, `skills.html`, `contact.html` and `README.md` must all be present.

## Step 9 – Demonstrate to the instructor

Show:
1. The repository page with all four files in `main`
2. The branches list (`feature/profile`, `feature/skills`, `feature/contact`)
3. The commit history (`git log --oneline`)
4. The merged Pull Requests (all marked **Merged**)

## Submission checklist

- [ ] GitHub repository URL
- [ ] Pull Request URLs
- [ ] Confirmation that all Pull Requests are merged
- [ ] Demonstration of each member's individual contribution
- [ ] Activity Completion Tracker updated (only after verification)

## Quick reference – upload a new project to GitHub

```bash
git init
git status
git add .
git commit -m "Initial commit"
git remote add origin <URL>
git push -u origin main
```
