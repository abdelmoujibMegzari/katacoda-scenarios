# Cloning the work repository

The first step for this tutorial is to create a git repository that CI pipeline builds and runs static code scanning against.
Lucky for you we have already created a git repository which you can fork and use in this tutorial.  
The repository is a maven project that contains one single java main class that prints "Hello world!" on the screen.

Let's start by forking the new repository:  
https://github.com/abdelmoujibMegzari/hello_world

For those of you unfamiliar with GitHub, open this link after you connect to your GitHub account.  
on the top right of the screen, you should see a fork button click on it.

![fork](assets/fork.png)

A new repository will be created on your account that is an exact copy of this one. It should be open automatically after you have clicked on the fork.

Next clone the repository into your local machine. For this tutorial, we suggest that you use the Katacodas terminal.
execute `git clone <repo>`


You can get the repository link by clicking the green button on Github on your repository.
![clone](assets/code.png)


Next, go to the newly cloned repository.
`cd hello_world`{{execute}}

**Bonus:**
You can try to run the program.

`mvn --batch-mode --update-snapshots verify`{{execute}}

`cd target/classes`{{execute}}

`java HelloWorld`{{execute}}

You can enter your name now but remember, only a Jedi will know the truth.

Solution for the easter egg at the end of the tutorial.
