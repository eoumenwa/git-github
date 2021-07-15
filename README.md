# git-github
Beginner's Stroll

The main file equals readme here
These are some of the projects I implemented during my Devops training with Dare.IO.
I am also using this read me file to track my learnings
At this a point, I am practicing how to setup vsc code and learning diff tool concept
Difftool did not seem to be working after setup..Error message is below
$ git difftool 210d4e5 5835c24
git config option diff.tool set to unknown tool: defualt-difftool
Resetting to default...

This message is displayed because 'diff.tool' is not configured.
See 'git difftool --tool-help' or 'git help config' for more details.
'git difftool' will now attempt to use one of the following tools:
opendiff kdiff3 tkdiff xxdiff meld kompare gvimdiff diffuse diffmerge ecmerge p4
merge araxis bc codecompare smerge emerge vimdiff nvimdiff

Viewing (1/1): 'Readme'
Launch 'vimdiff' [Y/n]? n
I entered no so as to troubleshoot. This has occured to me the best way to log my blockers going forward.
I will also be committing everyday as well

I just realized I wrongly spelt default as defualt (see line 6 above) and this caused the error above
Here is hoping that my difftool will work this time

On git branching. I need to have committed to the local repository before I can create a branch
I had to delete the .git folder to reset everything. Thinking of how to delete branches but this worked...

3/9/2021
Now practicing how to merge branches at local repo and push to remote. Merge changes in branches into main/master then main/master
into branches else your changes will be overwritten by old master/main. In essence, just merge new into old!
Also singly pushing a branch from local to remote without merging so as to maintain integrity of remote 
Created a new branch at githhub NewRemoteLocalFlowDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (pushToRemoteDemo)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git fetch origin
From https://github.com/eoumenwa/DefaultWeb_WorkingDirectory
 * [new branch]      NewRemoteLocalFlowDemo -> origin/NewRemoteLocalFlowDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch
  Feature02
  feature01
  feature03
* master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git checkout NewRemoteLocalFlowDemo

Switched to a new branch 'NewRemoteLocalFlowDemo'

Branch 'NewRemoteLocalFlowDemo' set up to track remote branch 'NewRemoteLocalFlo
wDemo' from 'origin'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git branch
  Feature02
* NewRemoteLocalFlowDemo
  feature01
  feature03
  master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$

On creating and merging pull requests and reviews at github.
This can be done from one branch to another but mostly done 
from change branch to master. Always check destination before merging
NewRemoteLocalFlowDemo was pulled into master at github
Next is to fetch and pull changes from REMOTE (github) to local

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git fetch origin
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 658 bytes | 18.00 KiB/s, done.
From https://github.com/eoumenwa/DefaultWeb_WorkingDirectory
   bdb20b5..38a10eb  master     -> origin/master

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git checkout master

Switched to branch 'master'
Your branch is behind 'origin/master' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)

$ git pull origin master

From https://github.com/eoumenwa/DefaultWeb_WorkingDirectory
 * branch            master     -> FETCH_HEAD
Updating bdb20b5..38a10eb
Fast-forward
 About.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git checkout NewRemoteLocalFlowDemo
Switched to branch 'NewRemoteLocalFlowDemo'
Your branch is up to date with 'origin/NewRemoteLocalFlowDemo'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git merge master
Updating 70b58b9..38a10eb
Fast-forward

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git push origin
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/eoumenwa/DefaultWeb_WorkingDirectory.git
   70b58b9..38a10eb  NewRemoteLocalFlowDemo -> NewRemoteLocalFlowDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$

On deleting local branches

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (NewRemoteLocalFlowDemo)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch
  Feature02
  NewRemoteLocalFlowDemo
  feature01
  feature03
* master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch -d Feature01
Deleted branch Feature01 (was bdb20b5).

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)

$ git branch
  Feature02
  NewRemoteLocalFlowDemo
  feature03
* master
  pushToRemoteDemo

Method 2
Using github


Method 3
Deleting a branch at origin from bash

On deleting a branch at Github (REMOTE) from Local BASH
Notes: After deleting a branch at github from BASH, you can still push the same branch back from local to github. 
Once your run git branch -d, it is gone unless you have it at github 

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git push origin --delete Feature03
To https://github.com/eoumenwa/DefaultWeb_WorkingDirectory.git
 - [deleted]         Feature03

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$
oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch -d Feature03
Deleted branch Feature03 (was bdb20b5).

Ok, I just deleted Feature02 from GITHUB and pushed another link to origin from local bash as below
oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch
  Feature02
  NewRemoteLocalFlowDemo
* master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git push -u origin Feature02
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'Feature02' on GitHub by visiting:
remote:    https://github.com/eoumenwa/DefaultWeb_WorkingDirectory/pull/new/Feature02
remote:
To https://github.com/eoumenwa/DefaultWeb_WorkingDirectory.git
 * [new branch]      Feature02 -> Feature02
Branch 'Feature02' set up to track remote branch 'Feature02' from 'origin'.

Next, I deleted Feature02 again from BASH as below
oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git push -u origin --delete Feature02
To https://github.com/eoumenwa/DefaultWeb_WorkingDirectory.git
 - [deleted]         Feature02

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$
To delete entirely*********************
oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch
  Feature02
  NewRemoteLocalFlowDemo
* master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch -d Feature02
Deleted branch Feature02 (was 4216b3d).

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch
  NewRemoteLocalFlowDemo
* master
  pushToRemoteDemo

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$

On deleting a branch that has changes that are not committed to origin----deleting a branch with force overide
oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git checkout -b Feature02
Switched to a new branch 'Feature02'

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ code details.html

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ code details.html

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git commit -am "Change one in feature 2"
[Feature02 bc75292] Change one in feature 2
 1 file changed, 3 insertions(+), 2 deletions(-)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ code details.html

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git commit -am "Second change in feature 2"
[Feature02 16089f3] Second change in feature 2
 1 file changed, 1 insertion(+)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ code details.html

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git commit -am "Final change in feature 2"
[Feature02 dfe2736] Final change in feature 2
 1 file changed, 1 insertion(+), 1 deletion(-)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git status
On branch Feature02
nothing to commit, working tree clean

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ code details.html

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git status
On branch Feature02
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   details.html

no changes added to commit (use "git add" and/or "git commit -a")

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git add .

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git status
On branch Feature02
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   details.html


oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git checkout master
error: Your local changes to the following files would be overwritten by checkou
t:
        details.html
Please commit your changes or stash them before you switch branches.
Aborting

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git branch -d Feature02
error: Cannot delete branch 'Feature02' checked out at 'C:/Users/oeume/Desktop/G
itPracs/DefaultWeb_WorkingDirectory'

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git commit -m "Test line added"
[Feature02 eda92c0] Test line added
 1 file changed, 1 insertion(+), 1 deletion(-)

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git branch -d Feature02
error: Cannot delete branch 'Feature02' checked out at 'C:/Users/oeume/Desktop/G
itPracs/DefaultWeb_WorkingDirectory'

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (Feature02)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch -d Feature02
error: The branch 'Feature02' is not fully merged.
If you are sure you want to delete it, run 'git branch -D Feature02'.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$ git branch -D Feature02
Deleted branch Feature02 (was eda92c0).

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Desktop/GitPracs/DefaultWeb_WorkingDirectory (master)
$

In summary, once changes have not been pushed to the remote
repo, you need to use branch -D and not -d

On deleting and restoring branches at github
When a branch is behind the master, there is nothing to commit. 
It is safe to delete any branch with zero commits ahead

gitprune and cleaning up references that no longer exist. 

Next is conflict merging, team branching and merging
Do I merge my branch to master locally to resolve the conflict?
Never.  Always pull from origin to your local master, 
then you merge master into your local branch, not your branch into master. 
On your local branch, resolve the conflict and push to GitHub, where you then merge to master via a pull request.
 Just like cyclical movement between thus explanined--pull origin >> master >> local branch >> resolve >>
 push to origin github >> merge/pull request  >> master

 On git clone
 Used the feature today
 Distracted by CRM concept on 14th. No commit

 ANSIBLE****************************************************************************************************

See ansible toddling repo
