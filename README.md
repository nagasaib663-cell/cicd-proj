# Secure CI/CD Demo – Security & Compliance in DevOps

## Overview
This project demonstrates a modern CI/CD pipeline that prioritizes security and compliance, using real automation tools to catch code vulnerabilities, leaked secrets, and enforce coding standards.

## Focus Areas & Tools

| Focus Area           | Description                                   | Tool/Workflow           |
|----------------------|-----------------------------------------------|-------------------------|
| Code Scanning        | Detect vulnerabilities in code on every push  | CodeQL (GitHub Actions) |
| Secrets Detection    | Prevent accidental leak of secrets/keys       | Gitleaks (GitHub Actions) |
| Compliance Checks    | Enforce Java coding standards & best practices| Checkstyle (GitHub Actions) |

## How It Works

- Every code change triggers GitHub Actions:
    - **CodeQL**: Scans for code vulnerabilities.
    - **Gitleaks:** Scans for exposed secrets (e.g., AWS keys, tokens).
    - **Checkstyle:** Enforces code style and best practices (Java).
- Results are displayed in the **Actions** and **Security** tabs for each commit.
- Example: If a secret key or poorly formatted code is committed, the corresponding workflow will fail and show an error log.

## How to Test

1. Commit code with a fake AWS key or secret to see Gitleaks in action.
2. Commit code with bad style (e.g., missing semicolon) to trigger Checkstyle.
3. Click into failed workflow run for details.

## Results
- [ ] No vulnerabilities and secret leaks: ✅ pipeline green.
- [ ] Any issue detected: pipeline fails, full log available for review.

## Contributors
- 
