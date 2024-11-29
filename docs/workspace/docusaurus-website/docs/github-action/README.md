# GitHub Action with local runner

## Description:

In this document, you will know how to use GitAction to

1. Build a image using local git runner

2. Auto deploy the image at local machine

## Requirement

Install Docker Desktop at local machine

GitHub repository in which contain an executable source code, and, it can be “docker build” successfully

## Setup:

1. Go to repository (e.g.: GitHub_LocalRunner) -> Setting -> Runner, click “New Self-hosted runner”

2. Following the step to start the runner at local machine

Download zip file: https://github.com/actions/runner/releases/download/v2.319.1/actions-runner-win-x64-2.319.1.zip

Unzip zip file

3. Go to unzipped directory

Open cmd, go to unzipped directory

Remark: if we want run the local runner 

Copy and run the `./config` command

Remark: if the runner is already configured, please either
Remove the configure by `config.cmd`, or
Unzip the file to another directory

4. Configure runner, to simplify, use default value

Remind: If you want to run the runner as a Service, you should
Run the terminal as admin
You may get “cannot start the service actions.runner. in a timely fashion” error when start the service

Use `run.cmd` to start runner. Runner is running

5. Configure GitHub action

Use `Action, select Docker image: Configure` as the template

Modify yml as follow: make sure it is run on "self-hosted". And the commit.

6. Check that GitAction is running, all job completed successfully

7. Check Runner is running locally: Job completed successfully

Docker desktop: containers started

Access localhost:5001 successfully

## Troubleshot 

### Issue 1: Build failed: running-scripts-is-disabled-on-this-system

https://stackoverflow.com/questions/64633727/how-to-fix-running-scripts-is-disabled-on-this-system

Solve: Issue 1 – execute `Set-ExecutionPolicy -Scope CurrentUser`



