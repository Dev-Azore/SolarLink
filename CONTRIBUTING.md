# SolarLink Contribution Guide

Welcome to the SolarLink project! To keep our code clean and our marketplace stable, we follow a professional workflow. Please read this guide before you start coding.

-## 1. Our Branching Strategy (GitFlow)
We use specific branches for different purposes. Never push directly to `main` or `develop`.

*   `main`: The "Production" branch. Only for finished, stable code.
*   `develop`: The "Working" branch. All team features are merged here first.
*   `feature/your-task`: Where you build new things (e.g., `feature/login-page`).
*   `hotfix/fix-name`: Only for emergency bug fixes in production.


## 2. How to Contribute

### Step 1: Get the latest code
Before starting, always make sure your local code is up to date:
```bash
git checkout develop
git pull origin develop
```

### Step 2: Create a Feature Branch
Create a new branch for your specific task:
```bash
git checkout -b feature/your-task-name
```

### Step 3: Work and Commit
Save your progress with clear messages:
```bash
git add .
git commit -m "feat: added solar company list view"
```

### Step 4: Push and Open a Pull Request (PR)
When you are done, push your branch to GitHub:
```bash
git push origin feature/your-task-name
```
Then, go to the GitHub website and open a **Pull Request** to merge your branch into `develop`.

---

## 3. Rules for a Successful Merge
To get your code merged, it must meet these criteria:
1.  Pass all CI Checks: Our automated system will check your code for errors. If it "fails loudly," you must fix the errors before we can merge.
2.  Code Review: At least one other team member must review and approve your PR.
3.  Resolve Conversations: If a reviewer leaves a comment, you must address it or discuss it until the conversation is resolved.

---

## 4. Project Structure (Mono-repo)
*   `/backend`: All API and server-side code.
*   `/frontend`: All user interface and client-side code.
*   `/infrastructure`: DevOps plans and architecture diagrams.

---

## Need Help?
If you get stuck with Git or the environment setup, please reach out to the DevOps Lead or check the `.env.example` file in the backend folder.

Happy Coding!