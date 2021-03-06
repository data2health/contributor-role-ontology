## Creating a branch and Pull Request

### Updating the local copy of the ontology with ‘git pull’

1. In the terminal, navigate to your local version of the ontology
~~~~
cd repos/contributor-role-ontology/src/ontology
~~~~
_Note: `repos` should be replaced with the folder name on your computer_

2. Type `git status`. You should see:

~~~
On branch [master] [or the name of the branch you are on]
Your branch is up-to-date with 'origin/master'.
~~~

3. If you’re not in the master branch, type: `git checkout master`

4. From the master branch, type: `git pull.` This will update your master branch, and all working branches, with the files that are most current on GitHub, bringing in and merging any changes that were made since you last pulled the repository using the command git pull.

### Creating a New Working Branch with ‘git checkout’

1. When starting to work on a ticket, or when making changes to the ontology, you should create a new branch of the repository to edit the ontology file.
2. **Make sure you are on the master branch before creating a new branch.** If the terminal window is not configured to display the branch name, type: `git status` to check which is the active branch. If necessary, go to master by typing `git checkout master.`
3. To create a new branch, type: `git checkout -b issue-NNNNN` in the terminal window. For naming branches, we recommend using the string ‘issue-‘ followed by the issue number. If you are not working on a ticket, create a branch name of your choice.

### Continuing work on an existing Working Branch
1. If you are continuing to do work on an existing branch, in addition to updating master, go to your branch by typing `git checkout [branch name].` Note that you can view the existing local branches by typing `git branch -l`.
2. OPTIONAL: To update the working branch with respect to the current version of the ontology, type `git pull origin master`. This step is optional because it is not necessary to work on the current version of the ontology; all changes will be synchronized when `git merge` is performed.

### Loading, navigating and saving the Ontology in Protégé
1. Before launching Protégé, make sure you are in the correct branch. To check the active branch, type `git status`. You can also see the branch you are on in Protege, in the lower left corner (in Protege 5.5).
2. In Protege, click on the ‘File’ pulldown. Open the file: cro-edit.obo. The first time, you will have to navigate to repos/contributor-role-ontology/src/ontology. Once you have worked on the file, it will show up in the menu under ‘Open’/’Recent’.
3. Make your edits in Protege (see [CRO editors guide]()).
4. Use File > Save to save your changes.

### Committing, pushing and merging your changes to the repository

1. Review: Changes made to the ontology can be viewed by typing `git diff` in the terminal window. If there are changes that have already been committed, the changes in the active branch relative to master can be viewed by typing `git diff master`.

2. Commit: Changes can be committed by typing: `git commit -a -m ‘Meaningful message addresses #ticketnumber’`.

- For example:
~~~
   git commit - a -m ‘add new term 'software project management'. Address #26"’ 
~~~
3. This will save the changes to the cro-edit.obo file. 

NOTE: The word ‘addresses’ is a magic word in GitHub; when used in combination with the ticket number, it will automatically reference the ticket in GitHub. You can also use `closes` or `fixes` and when the file is merged in GitHub, it will close issue number 26. Learn more on this GitHub Help Documentation page about [Closing issues via commit messages](https://help.github.com/en/articles/closing-issues-using-keywords).

- `addresses, closes and fixes` are case-insensitive.

- NOTE: It is also possible to type a longer message than allowed when using the ‘-m’ argument; to do this, skip the -m, and a vi window (on mac) will open in which an unlimited description may be typed.

4. Push: To incorporate the changes into the remote repository, type: `git push origin mynewbranch`

Example:

 `git push origin issue-26`

**TIP:** Once you have pushed your changes to the repository, they are available for everyone to see, so at this stage you can ask for feedback.

### Pull Request

1. In your browser, return to the [CRO repository on GitHub](https://github.com/data2health/contributor-role-ontology).
2. You will see your commit listed at the top of the page in a light yellow box. If you don’t see it, refresh your browser.
3. Click the green button ‘Compare & pull request’ on the right.
4. You may now add comments and ask a colleague to review your pull request. If you want to have the ticket reviewed before closing it, you can select a reviewer for the ticket before you make the pull request by clicking on the ‘Reviewers’ list and entering a GitHub identifier (e.g. @marijane). The reviewer will be notified when the pull request is submitted. Since the Pull Request is also a GitHub issue, the reviewer’s comments will show up in the dialog tab of the pull request, similarly to any other issue filed on the tracker.
5. The diff for your file is at the bottom of the page. Examine it as a sanity check.
6. Click on the green box ‘Pull request’ to generate a pull request.
7. Wait for the Travis checks to complete (this can take a few minutes). If the Travis checks failed, go back to your working copy and correct the reported errrors.
8. If you have admistrative rights, merge if the Travis checks are succesful and if you are done working on that branch, merge the pull request. Confirming the merge will close the ticket if you have used the word 'closes' or ‘fixes’ in your commit comment.  
9. Delete your branch on the repository using the button on the right of the successful merge message.
10. You may also delete the working branch on your local copy. _Note that this step is optional._ However, if you wish to delete branches on your local machine, in your terminal window:

- Go back to the master branch by typing git checkout master.
- Update your local copy of the repository by typing `git pull origin master`
- Delete the branch by typing `git branch -d workingbranchname.` 
Example: `git branch -d issue-26`

_This content was adopted from the [Gene Ontology](https://go-ontology.readthedocs.io/en/latest/DailyWorkflow.html)._

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
