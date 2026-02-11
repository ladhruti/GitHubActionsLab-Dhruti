
# GitHub Actions Lab – Automated Workflows


I used the `needs` keyword in Part A to design a process that illustrates job dependencies. A push to the main branch initiates the workflow.

This workflow consists of three jobs:
- construct  
- test  
- deploy These tasks execute in the following sequence:

Build, test, and then deploy  

The `build` job, the `test` job, and the `deploy` job are dependent on each other. This guarantees that each job doesn't begin until the last one has finished satisfactorily.

Running on `ubuntu-latest`, each task has several phases that use sleep functions and echo commands to mimic actual work.

Important ideas illustrated in Part A:

- `needs` establishes inter-job dependencies  The operating system environment is defined by `runs-on`.  
- The workflow trigger is `push`.  
--- ## Workflow 2: Multi-Platform Testing in Part B

To illustrate parallel execution, I developed a workflow in Part B that executes separate jobs on various operating systems.

A pull request to the main branch initiates this process.

Three separate positions exist:
Ubuntu-job, which operates on Ubuntu-latest  
- windows-job (uses the most recent version of Windows)  
- macos-job (operates on the most recent version of macos)  

Every job carries out the subsequent actions:
Utilizing `actions/checkout@v4`, the repository is checked out.  Information about the operating system is displayed.  Executes a command specific to the OS  
Produces a basic file  - Shows the contents of the file  

All three processes execute concurrently because this workflow does not employ the `needs` keyword.
Important ideas given in Part B:

When `needs` are absent, jobs can operate concurrently.  By using `pull_request` as the workflow trigger  
Different operating systems are specified by -{runs-on`.  
- `actions/checkout@v4` verifies the code of the repository  
---## Difficulties Encountered

I ran across some minor YAML indentation and workflow trigger configuration issues throughout this lab. These were fixed by closely examining the indentation and making sure the right branch was used when generating pull requests.
The ---

This experiment uses GitHub Actions to illustrate both parallel and dependent task execution.
