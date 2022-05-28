# Intro:
DevSecOps is an approach that aims to integrate security as a shared responsibility throughout the entire development lifecycle.
Part of that is early checking code if it has vulnerabilities or issues which is called "Static code scanning".

# Outcome

This tutorial will teach you how as a software engineer to think about security when you write your code by performing static code scanning.
So by implementing a CI that builds, and runs static code scanning, part of DevSecOps is achieved. Using tools like Github Action, and CodeQL.

# Tools
- Github action: CI/CD managed tool provided by Github that enables engineers from implementing fully automated pipelines.
- CodeQL: A code scanning engine implemented by Github, that gives engineers the ability to scan code for issues, and vulnerabilities.
- Java console app.

# CI Flow
Each time engineer commits a line of code to the repository. Github Action CI pipeline is triggered that will build the code, then it will use CodeQL to perform static code scanning on the whole code. If any issues are found, the build fails until engineers fix everything.

# Tutorial Steps
1- Prepare code repository.

2- Create Github Action Pipeline.

3- Add the pipeline to the repository.

4- Test the pipeline.

5- Add CodeQL step into the pipeline to perform static code scanning.

6- Examine the results.