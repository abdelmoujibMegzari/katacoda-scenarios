# Go and check result on the pipeline

Go to actions tab.  

There your new commit should be marked in green.  

![action](assets/actions2.png)

If the color is yellow it's still building give it some time.

Now go to Security tab, and see if we got anything dangerous in the code.
![action](assets/security.png)

Nice!
Looks pretty clean..

Now let's take a look at the different steps in our pipeline

![action](assets/codeQLSteps.png)

If we look at the perform codeQL analysis step, we can notice more information concerning the analysis.
![action](assets/codeQLAnalysis.png)

Finally, if we check the running queries for java, we can see all the vulnerabilities that codeQL has checked for.
![action](assets/checkedVulnerabilities.png)
