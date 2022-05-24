# Intro:
DevSecOps is an approach that aims to integrate security as a shared responsibility throughout the entire IT lifecycle.
Part of that is early checking code if it has vulnerabilities or issues which is called "Static code scanning".

# Outcome

This tutorial will teach you how as a software engineer to think about security when you write your code by performing static code scanning.
So by implementing a CI that has a step to run static code scanning, part of DevSecOps is achieved. Using tools like Github Action, and CodeQL.

# Tools
- Github action: CI/CD managed tool provided by Github that enables engineers from implementing fully automated pipelines. a java application, and run static code scanning to make sure that you are shipping proper code.
- CodeQL: is a code scanning engine implemented by Github, that gives engineers the ability to scan code for issues, and vulnerabilities.

# CI Flow
Each time engineer commits a line of code to the repository. Github Action CI pipeline is triggered that will build the code, then it will use CodeQL to perform static code scanning on the whole code. If any issues are found, the build fails until engineers fix everything.