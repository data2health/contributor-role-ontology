### Creating a new branch

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

4. From the master branch, type: `git pull.` This will update your master branch, and all working branches, with the files that are most current on GitHub, bringing in and merging any changes that were made since you last pulled the repository using the command git pull. You will see something like this:
~~~
remote: Enumerating objects: 160, done.
remote: Counting objects: 100% (160/160), done.
remote: Compressing objects: 100% (106/106), done.
remote: Total 241 (delta 132), reused 54 (delta 54), pack-reused 81
Receiving objects: 100% (241/241), 43.71 KiB | 3.12 MiB/s, done.
Resolving deltas: 100% (177/177), completed with 4 local objects.
From https://github.com/data2health/contributor-role-ontology
   f4c4645..b07f490  master     -> origin/master
Updating f4c4645..b07f490
Fast-forward
 docs/pages/contributors.md                       |   4 +-
 docs/pages/editors.md                            |  22 ++-
 docs/pages/editorsguide/CROeditorsguide.md       | 194 +++--------------------
 docs/pages/editorsguide/howtomakeatermrequest.md |  19 ++-
 docs/pages/editorsguide/mireoting.md             |  18 +++
 docs/pages/editorsguide/obsoleting.md            |  60 +++++++
 docs/pages/editorsguide/pullrequest.md           |  27 ++++
 docs/pages/editorsguide/settingup.md             |  66 ++++++++
 8 files changed, 226 insertions(+), 184 deletions(-)
 create mode 100644 docs/pages/editorsguide/mireoting.md
 create mode 100644 docs/pages/editorsguide/obsoleting.md
 create mode 100644 docs/pages/editorsguide/pullrequest.md
 create mode 100644 docs/pages/editorsguide/settingup.md
~~~



### Pull Request

_this content is under development_

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
