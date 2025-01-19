# Step-by-Step Notes: Creating a GitHub Actions Workflow

## 1. **Introduction**
   - This video demonstrates how to create the first workflow using GitHub Actions.
   - Key concepts covered:
     - **Triggers:** Actions triggered by events like pull requests or commits.
     - **Runner:** The machine where the workflow executes.
     - **Workflow Syntax:** Understanding jobs and steps.

---

## 2. **Prerequisites**
   - A GitHub account.
   - A repository created in GitHub (can include application source code, scripts, and workflows).

---

## 3. **Exploring GitHub Actions**
   - **Actions Feature:** Enables workflows for applications.
     - Workflows can:
       - Automate commands in pull requests.
       - Commit directly to repositories.
   - Templates available for:
     - Building Docker images.
     - Compiling applications (e.g., .NET, desktop apps).
     - Deploying to cloud providers (Azure, AWS, GCP, etc.).
     - Kubernetes and on-premises deployments.

---

## 4. **Creating a Simple Workflow**
   1. Navigate to **Actions** in your repository.
   2. Select a **template** or start a new simple workflow.
   3. The workflow is stored in `.github/workflows/main.yml`.

---

## 5. **Understanding Workflow Syntax**
   - YAML structure for a workflow:
     - **Name:** Identifies the workflow.
     - **`on:`** Specifies triggers:
       - `push`: Triggered on commits to branches like `main` or `dev`.
       - `pull_request`: Triggered on pull requests.
       - `workflow_dispatch`: Allows manual triggering.
     - **`jobs:`** Defines tasks:
       - Each job runs on a **runner** (virtual machine).
       - Supported runners: `ubuntu-latest`, `windows-latest`, `macos-latest`.

---

## 6. **Defining Steps in a Workflow**
   - **Checkout Source Code:**
     - Use the `actions/checkout` step to fetch the repository.
     - Example:
       ```yaml
       steps:
         - name: Checkout code
           uses: actions/checkout@v3
       ```
   - **Run Scripts:**
     - Single-line script:
       ```yaml
       - name: Run a script
         run: echo "Hello World"
       ```
     - Multi-line script:
       ```yaml
       - name: Run multiple commands
         run: |
           echo "Line 1"
           echo "Line 2"
       ```

---

## 7. **Testing and Running Workflows**
   - Save and commit the workflow file.
   - Workflow triggers:
     - Automatically on events like `push` or `pull_request`.
     - Manually via the **Run Workflow** button in the GitHub UI.

---

## 8. **Viewing Workflow Execution**
   - Check the **Actions** tab for triggered workflows.
   - Steps displayed in the UI:
     - **Setup job:** Finds and initializes the runner.
     - **Execute steps:** Runs defined actions/scripts.
     - **Cleanup job:** Removes temporary files and releases the runner.

---

## 9. **Additional Notes**
   - GitHub Actions Marketplace:
     - Explore reusable actions (e.g., `actions/checkout`).
   - Runners:
     - Dedicated virtual machines for executing workflows.

---

## 10. **Conclusion**
   - A simple GitHub Actions workflow includes:
     - Defining triggers.
     - Specifying jobs and steps.
     - Using available actions and running scripts.
   - Workflows enhance automation and streamline CI/CD processes.

---

