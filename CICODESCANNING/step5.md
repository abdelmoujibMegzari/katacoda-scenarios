# Adding static scanning

Congratulation, now you had your first CI pipeline that builds a java app.
Now, time to take it to the next level and add the static code scanning part.

So again, Open `workflow.yml`{{open}}

Then replace the workflow definition with the below
Which basically:

- Initialize CodeQL.
- Build the code.
- Run static scanning.

<pre class="file" data-filename="workflow.yml" data-target="prepend">
name: Java CI

on:
  push:
    branches: [main]
  pull_request:
    # The branches below must be a subset of the branches above
    branches: [main]
  schedule:
    - cron: "25 11 ** 2"

jobs:
  analyze:
    name: Analyze
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write

    strategy:
      fail-fast: false
      matrix:
        language: ["java"]

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      # Initializes the CodeQL tools for scanning.
      - name: Initialize CodeQL
        uses: github/codeql-action/init@v2
        with:
          languages: ${{ matrix.language }}

      - name: Set up JDK 14
        uses: actions/setup-java@v3
        with:
          java-version: "14"
          distribution: "adopt"
      - name: Build with Maven
        run: mvn --batch-mode --update-snapshots verify

      - name: Perform CodeQL Analysis
        uses: github/codeql-action/analyze@v2
</pre>

Now add the changes:

Add the file to git : `git add .`{{execute}}

Commit the changes: `git commit -m "Static scanning in pilpline"`{{execute}}  

Finally push your changes: `git push`{{execute}}
