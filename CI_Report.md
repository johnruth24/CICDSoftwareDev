Continuous Integration Pipeline Report
Automated Build Pipeline with CI Server  


1. Introduction
Continuous Integration (CI) is a development practice where code changes are automatically built and tested every time they are pushed to a shared repository. CI helps teams detect integration issues early, maintain code quality, and ensure that the application remains in a deployable state throughout development.

This project implements a CI pipeline using GitHub Actions, a cloud‑based CI/CD platform integrated directly into GitHub. The pipeline automatically installs dependencies, runs tests, builds the application, and fails when tests do not pass. This setup simulates a professional development workflow and demonstrates how CI improves reliability and collaboration.

2. CI Platform Selection


It integrates seamlessly with GitHub repositories

It requires no external server setup

It uses simple YAML configuration

It provides free hosted runners for small projects

It offers clear logs, status badges, and workflow history



3. Pipeline Stages
The CI pipeline follows three major stages:

Stage 1: Source
Triggered automatically when:

Code is pushed to main or dev

A pull request is opened targeting main

This ensures that all changes are validated before merging.

Stage 2: Build
The pipeline:

Checks out the repository

Installs dependencies using npm ci

Builds the application using npm run build

This guarantees that the project compiles correctly on a clean environment.

Stage 3: Test
Automated tests run using npm test.
If any test fails, the pipeline stops immediately.

This “fail fast” behavior prevents broken code from entering the main branch.

4. YAML Configuration Explanation
Below is the CI configuration file used in this project:

yaml
name: CI Pipeline

on:
  push:
    branches: [ "main", "dev" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test

      - name: Build application
        run: npm run build
Explanation of Key Sections
on:  
Defines triggers. The workflow runs on pushes to main and dev, and on pull requests targeting main.

jobs:  
Contains the pipeline job. Only one job is used: build-and-test.

runs-on:  
Specifies the runner environment. ubuntu-latest is a clean Linux VM provided by GitHub.

steps:  
Each step performs part of the pipeline:

Checkout code

Install Node.js

Install dependencies

Run tests

Build the application

If any step fails, the entire pipeline fails.

5. Status Badge

markdown
![CI Pipeline](https://github.com/<your-username>/<your-repo>/actions/workflows/ci.yml/badge.svg)
This badge updates automatically and displays whether the latest build passed or failed.

6. Branch-Specific Triggers
The pipeline is configured to:

Run on push to main and dev

Run on pull requests targeting main

This ensures:

Developers can test changes on dev

Only validated code reaches main

Pull requests cannot be merged if CI fails

This setup mirrors real‑world development workflows.

7. Build Logs Visibility
GitHub Actions provides detailed logs for each step:

Dependency installation logs

Test results

Build output

Error messages

These logs help developers quickly identify issues and fix them before merging.

8. How CI Prevents Integration Issues
CI reduces integration problems by:

Running tests automatically on every commit

Ensuring consistent build environments

Catching bugs before merging

Preventing broken code from entering main

Providing immediate feedback to developers

Teams using CI experience fewer failures and faster development cycles because issues are detected early rather than after merging.

