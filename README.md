# DevOps Onboarding: GitHub Actions Workflow Simulation

This repository was created as part of the team onboarding task assigned by Samuel. It serves to establish local Git configurations, terminal usage proficiency, and an automated continuous integration (CI) workflow using GitHub Actions.

## 🚀 Getting Started

### Prerequisites
* A Unix-like terminal environment (Bash, Zsh, or Git Bash for Windows).
* **Git** installed and configured locally according to company resource guides.

### Local Installation & Setup
1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd YOUR_REPO_NAME
   ```

2. **Configure your Git identity globally (if not already done):**
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

---

## ⚙️ CI/CD Workflow Architecture

The repository contains an automated workflow powered by **GitHub Actions** located in `.github/workflows/main.yml`.

### Triggers
* **Push**: Executes automatically whenever code is pushed to the `main` or `master` branches.
* **Pull Request**: Runs when code changes are targeted at production branches.
* **Manual**: Can be triggered manually via the GitHub interface using the `workflow_dispatch` event.

### Job Sequence
* **Environment Verification**: Spins up a virtual Ubuntu runner (`ubuntu-latest`).
* **Code Checkout**: Clones the source tree into the runner workspace using `actions/checkout@v4`.
* **Variable Validation**: Logs repository metadata utilizing built-in GitHub context variables (`github.actor`, `github.ref`).

---

## 🛠️ Verification & Support

To verify that the automated systems are functioning correctly:
1. Navigate to the **Actions** tab on the GitHub repository landing page.
2. Confirm that the last run displays a green success badge.

*For questions or issues regarding this setup, please reach out to Team Lead Samuel or post an inquiry directly in the Microsoft Teams channel.*
