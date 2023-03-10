## Setup Instructions:

1. Run `npm install` to install the dependencies
2. Install docker desktop https://www.docker.com/products/docker-desktop/
3. Run docker-compose -f db_init.yaml up;  
4. Open browser at localhost:8080;  
5. Login:
    - System: PostgreSQL  
    - User: postgres  
    - Password: example
6. Run `npm run dev` to start the dev server at port 3000

*Basic scripts are defined in `./package.json`.*

[] TODO : `Unexpected console statement` lint error is disabled. That should be enabled before shipping for production which means that the code base should have no `console.log` statements.  
[] TODO/IDEA : We should separate the codebase / volume for the database container into a separate directory (and repository), no ?

### If db schema doesn't load in container:
1. Delete the container.
2. Delete the associated volume.
3. Run docker-compose -f db_init.yaml up;

## Github Workflow
### If you start working on a fresh issue

1. Check github repo issues page.

2. Select an issue to work on.
![1  Check out issues](https://user-images.githubusercontent.com/40914437/224488666-f1be03df-e7b4-4d35-8987-5bdca970fa61.jpg)

3. Comment on the issue that you will work on it and assign yourself (if you haven’t been assigned to the issue already);
![2  Assign issue](https://user-images.githubusercontent.com/40914437/224488691-2b47d069-7510-4244-b88e-493b307cd9fa.jpg)

4. If you don’t already have the repository on your local machine, clone it:
  - On the repository’s main page click on the green code button and copy the https link;
        ![3  Get repo link](https://user-images.githubusercontent.com/40914437/224488739-c342f293-f382-4ed2-aec7-2838e69ea1df.jpg)
  - In your terminal in a directory of your choice run `git clone <link_to_repo>` in order to copy the github repository to your local machine;
![4  Clone the repo](https://user-images.githubusercontent.com/40914437/224488745-25ec0c06-f76b-4e7a-bb20-b89dca5ce4f5.jpg)
  - Go to the newly created project folder;
![5  Go to directory](https://user-images.githubusercontent.com/40914437/224488750-3e270cee-0734-4bc1-90cb-12ae7abce7fd.jpg)

6.  Create a new branch for the feature that you want to work on.
  - You will have to create a branch on the remote repo (on Github) and one locally on your machine.
  - On your terminal run `git checkout -b <branch_name>` . The branch name should be composed of the issue number and a relevant name (can use the name of the issue). In this case `git checkout -b 6-test-issue`. This command will create a new branch and switch to it.
  - You can check the branches on your machine by using the command `git branch`. The current working branch will be highlighted (At least it is in my case, I have no idea how it looks on the Mac terminal).
  - If you want to switch between branches just use `git checkout <branch_name>`;

7. Start coding.

8. As you work on the issue. Commit your changes to the local repository.
  - Run `git add .`
  - Run `git commit -m 'Short message describing what you did'`
  - Run `git push --set-upstream origin <branch_name>`  - Pushes the changes to the remote repository. In our case the command will be `git push --set-upstream origin 6-test-issue`. *The `--set-upstream` flag is necesarry only on the first push. After the initial push you can just use `git push <branch_name>`*

9. In order to implement the changes made in the new new branch back to the `main` branch we need to create a Pull Request.
  - Switch to the newly created feature branch and then click on ‘Compare & Pull Request’.
![6  Switch to branch](https://user-images.githubusercontent.com/40914437/224488810-8d5b029d-f03d-4890-b895-11f3e716603c.jpg)
  - Write a comment detailing your work and click ‘Create pull request’.
![7  Create pull request](https://user-images.githubusercontent.com/40914437/224488821-04d35fd8-f07f-4cfd-b925-0fcd13448ff6.jpg)

10. After approval from the other team members, your branch will be merged with the main branch of the repo.

11. Delete the feature branch after it’s been merged to the main branch.
  - Switch to the main branch (you cannot delete the branch that you are in) `git checkout main`
  - Delete the feature branch locally `git branch -d 6-test-issue`
  - Delete the feature branch from the remote repo `git push origin --delete 6-test-issue`
