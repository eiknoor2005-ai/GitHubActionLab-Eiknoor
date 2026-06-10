# GitHub Actions Lab - Eiknoor

# Introduction

For this lab, I created two GitHub Actions workflows to learn how automated workflows work in GitHub. The first workflow focuses on job dependencies, while the second workflow demonstrates running jobs on multiple operating systems.

---

## Workflow 1 - Dependent Jobs Workflow

The purpose of this workflow is to show how jobs can depend on one another using the `needs` keyword.

This workflow runs whenever changes are pushed to the master branch.

The workflow contains three jobs:

* **Build** – simulates building the application.
* **Test** – runs after the build job is completed.
* **Deploy** – runs after the test job is completed.

The jobs execute in the following order:

**Build → Test → Deploy**

This helped me understand how GitHub Actions can control the order in which tasks are performed.

---

## Workflow 2 - Multi Platform Workflow

The purpose of this workflow is to test the workflow on different operating systems.

This workflow runs when a pull request is created for the master branch.

The workflow contains three independent jobs:

* **ubuntu-job**
* **windows-job**
* **macos-job**

Each job checks out the repository, displays operating system information, creates a simple text file, and displays its contents.

Since these jobs do not depend on one another, they run at the same time. This demonstrated how GitHub Actions can perform tasks in parallel.

---

## Key Concepts Learned

During this lab, I learned several important GitHub Actions concepts:

* **needs** – used to create dependencies between jobs.
* **runs-on** – specifies which operating system a job will run on.
* **pull_request** and **push** triggers – determine when workflows are executed.
* Parallel job execution when no dependencies are defined.

---

## Challenges Faced

One issue I encountered was that my workflows were not running initially. After checking the workflow files, I realized that the workflows were configured for the **main** branch while my repository was using the **master** branch.

I also needed some time to understand the difference between workflows triggered by a push event and workflows triggered by a pull request.

---

## How I Resolved the Issues

To fix the problem, I updated the workflow files to use the correct branch name and then pushed the changes again. I used the GitHub Actions page and workflow logs to verify that everything was running correctly.

---

## Conclusion

This lab provided practical experience with GitHub Actions, workflow automation, job dependencies, pull request workflows, and multi-platform testing across Ubuntu, Windows, and macOS environments.
