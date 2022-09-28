1 - Introduction to GitHub Actions
In this lab you will update and run your first workflow.

Duration: 5-10 minutes

References:

Events that trigger workflows
Adding an action to your workflow
1.1 Update the workflow to trigger when a change is made to the labs folder on main branch
Open the workflow file github-actions-demo.yml
Edit the file and copy the following YAML content after line 4:
  push:
    branches:
      - main
    paths:
      - 'labs/**'
Commit the workflow changes into the main branch
Change a file inside the folder labs
Commit the changes into the main branch
Go to Actions and see the details of your running workflow
1.2 Add steps to your workflow
Open the workflow file github-actions-demo.yml
Edit the file and copy the following YAML content at the end of the file:
        # This step uses GitHub's hello-world-javascript-action: https://github.com/actions/hello-world-javascript-action
      - name: Hello world
        uses: actions/hello-world-javascript-action@v1
        with:
          who-to-greet: "Mona the Octocat"
        id: hello
      # This step prints an output (time) from the previous step's action.
      - name: Echo the greeting's time
        run: echo 'The time was ${{ steps.hello.outputs.time }}.'   
Optional remove the paths to trigger the workflow on any push to main branch
Commit the changes into the main branch
If not step 3), change a file inside the folder labs and commit the changes into the main branch
Go to Actions and see the details of your running workflow
