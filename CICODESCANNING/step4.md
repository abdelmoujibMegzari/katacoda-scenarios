# adding the  java build with maven pipeline
open `workflow.yml`{{open}}
and copy this code into workflow.yml
<pre class="file" data-filename="workflow.yml" data-target="prepend">
name: Java CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - name: Set up JDK 14
        uses: actions/setup-java@v3
        with:
          java-version: '14'
          distribution: 'adopt'
      - name: Build with Maven  
        run: mvn --batch-mode --update-snapshots verify
</pre>

this code specify that every time a new element is pushed on the repository the folowing 3 steps thould be executed:  

1-The checkout step downloads a copy of your repository on the runner.  
2-The setup-java step configures the Java 11 JDK by Adoptium.  
3-The "Build with Maven" step runs the Maven package target in non-interactive mode to ensure that your code builds, tests pass, and a package can be created. 

now add the file to git : `git add workflow.yml`{{execute}}
commit the changes: `git commit -m "new pilpline"`{{execute}}
and finally push your changes: `gir push`{{execute}}
