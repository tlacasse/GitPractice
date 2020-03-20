# GitPractice
example workflow

1. Fork this repository on github.

2. Clone your fork. In a terminal in some folder to store repositories:

> git clone https://github.com/<your_username>/GitPractice.git

3. Enter the repo directory:

> cd GitPractice

4. Add this "master" repository as a remote:

> git remote add upstream https://github.com/tlacasse/GitPractice.git

5. Check the results, see your remote (fork) is named "origin" and the master one is named "upstream":

> git remote -v

6. Switch to master branch (which you are already on, but practice):

> git checkout master

7. Get all changes from the remotes:

> git fetch --all

8. Get current "master" code (be careful with any `git reset --hard`, but should be safe here):

> git reset upstream/master --hard

9. Create a new feature development branch:

> git checkout -b <branch>

10. Make sure you have the lastest changes before each session of development, (see `rebase -i` explained later):

> git fetch --all

> git rebase upstream/master -i

11. Make a change to the file `testfile.txt`, where it says `<make change here>`.

12. Stage your changes, I recommend using some other software for this, to better specify which files to stage and 
even which individual lines. Else research `git add`.

13. Commit the staged changes:

> git commit -m "<message>"

14. Push to your fork:

> git push origin <branch>

15. *To practice merge commits*, at the previous point there was `git rebase upstream/master -i`, but for practice we will do:

> git rebase upstream/otherwork -i

16. Here in the *interactive rebase* you can make changes to commit history, for now just exit the editor.

17. You should get a merge conflict, because two people worked on the same bit of code. In an file editor, you can
choose to keep their changes or your changes. Choose what is appropriate, but here just pick one, and recommit the commit.

18. Continue on:

> git rebase --continue

19. This is where you continue development, but any time history is rewritten, you must force push to your remote branch to overwrite it:

> git push origin <branch> --force

20. And you should be done. That is the general development process.

21. Finally you will want to create a pull request from your fork to the original repository (done on github). Never push directly to master.
