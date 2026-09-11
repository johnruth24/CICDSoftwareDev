# Git Workflow Standardization CI/DI

## Overview
This Procedure ensures that Developers follow the process of git workflow, while learning how to collaborate, integrate their code with the main code, and support Continuous  (CI).

---

## 1. Branching 


---

## 2. Commit Message Standards 




---

## 3. Merge Approval Process

1. Create a feature branch  
2. Commit changes using Conventional Commits  
3. Push branch to GitHub  
4. Open a Pull Request  
5. CI pipeline runs automatically  
6. Reviewer checks code quality and tests  
7. Developer addresses feedback  
8. Reviewer approves  
9. Merge using **Squash Merge**  
10. Delete the feature branch  

---

## 4. Branch Protection Rules

The `main` branch is protected to ensure stability.

### Required Rules
- Require pull request before merging  
- Require at least 1 approving review  
- Require status checks to pass  
- Require branches to be up to date  
- Restrict who can push  
- Prevent branch deletion  

---

## 5. Continuous Integration (CI)

CI runs automatically on:

- Pull requests  
- Pushes to feature branches  
- Merges into main  

### CI Tasks
- Install dependencies  
- Run linting  
- Run tests  
- Build validation  

---

## 6. Testing Requirements

- All new features must include automated tests  
- Tests run automatically in CI  
- Test failures block merging  
- Developers fix broken tests immediately  

---

## 7. Build & Deployment Automation

- Build process is fully automated  
- CI pipeline produces deployable artifacts  
- No manual build steps  

---

## 8. Infrastructure & Environment Management

- Environment configuration stored in version control  
- Infrastructure changes follow PR + review process  
- Build artifacts remain identical across environments  

---





