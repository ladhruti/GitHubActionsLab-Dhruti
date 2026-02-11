
# GitHub Actions Lab – Automated Workflows

## Part A – Workflow 1: Job Dependencies

In Part A, I created a workflow that demonstrates job dependencies using the `needs` keyword. The workflow is triggered on a push to the main branch.

There are three jobs in this workflow:

- build  
- test  
- deploy  

These jobs run in the following order:

build → test → deploy  

The `test` job depends on the `build` job, and the `deploy` job depends on the `test` job. This ensures that each job waits for the previous job to complete successfully before starting.

Each job runs on `ubuntu-latest` and includes multiple steps to simulate real work using echo commands and sleep functions.

Key concepts demonstrated in Part A:

- `needs` creates dependencies between jobs  
- `runs-on` defines the operating system environment  
- `push` is used as the workflow trigger  

---

## Part B – Workflow 2: Multi-Platform Testing

In Part B, I created a workflow that runs independent jobs on different operating systems to demonstrate parallel execution.

This workflow is triggered on a pull request to the main branch.

There are three independent jobs:

- ubuntu-job (runs on ubuntu-latest)  
- windows-job (runs on windows-latest)  
- macos-job (runs on macos-latest)  

Each job performs the following steps:

- Checks out the repository using `actions/checkout@v4`  
- Displays operating system information  
- Runs an OS-specific command  
- Creates a simple file  
- Displays the file content  

Since no `needs` keyword is used in this workflow, all three jobs run simultaneously.

Key concepts demonstrated in Part B:

- Absence of `needs` allows jobs to run in parallel  
- `pull_request` is used as the workflow trigger  
- `runs-on` specifies different operating systems  
- `actions/checkout@v4` checks out repository code  

---

## Challenges Faced

During this lab, I encountered minor YAML indentation issues and workflow trigger configuration problems. These were resolved by carefully reviewing indentation and ensuring the correct branch was used when creating pull requests.

---

This lab demonstrates both dependent job execution and parallel job execution using GitHub Actions.
