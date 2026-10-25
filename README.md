
CI Quality Gate & Reporting Workflow
This project implements a Continuous Integration (CI) pipeline with automated quality gates using GitHub Actions and SonarCloud.

Workflow Instructions
The CI pipeline runs automatically on:

Pushes to main and dev  
Pull requests targeting main  

Workflow Steps  
Checkout repository  
Fetches full git history to enable SonarCloud SCM analysis.

Set up Python environment  
Uses Python 3.12 for linting and testing.

Install dependencies  
Enforces binary‑only installation for security and reproducibility.

Linting (flake8)  
Ensures no linting errors are present.

Run tests with coverage  
Generates coverage.xml for SonarCloud.

Normalize coverage paths  
Fixes GitHub runner paths so SonarCloud can map coverage correctly.

Upload coverage report  
Stores coverage artifacts for review.

Set up JDK  
Required for SonarCloud scanner.

SonarCloud Scan  
Performs:  
- Code analysis  
- Coverage reporting  
- Vulnerability scanning  
- Quality Gate evaluation  

Quality Gates Enforced  
Minimum coverage threshold (configured in SonarCloud)  
Zero critical vulnerabilities  
No linting errors  
Build must succeed before merge  

Branch Protection  
GitHub branch protection rules require:  
- SonarCloud Code Analysis  
- build-and-test workflow  
- Passing CI checks before merge  

Artifacts Generated  
Coverage report (coverage.xml)  
SonarCloud analysis results  
CI pipeline success logs  

![CI + Quality Gates](https://github.com/johnruth24/CICDSoftwareDev/actions/workflows/cidi5-quality.yml/badge.svg)
![CI Pipeline](https://github.com/johnruth24/CICDSoftwareDev/actions/workflows/cidi5-quality.yml/badge.svg)

# CICDSoftwareDev
Software Development class

PR test update


![CI + Quality Gates](https://github.com/johnruth24/CICDSoftwareDev/actions/workflows/ci-quality.yml/badge.svg)

HEAD
![CI Pipeline](https://github.com/johnruth24/CICDSoftwareDev/actions/workflows/ci.yml/badge.svg)

# CICDSoftwareDev
Software Development class
3f9e9c6b3ff72931ddd11c0d7d6a0dafaaca48d5
PR test update
