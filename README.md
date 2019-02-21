# git-recipes
## Common GIT Recipes

### Analyzing a repository with git log and shortlog commands

The command that prints the number of commits in the repository

`$ git log --pretty=oneline | wc -l`

The command that prints the number of contributors

`$ git shortlog -s | wc -l`

The command that produces the number of days during which contributions were made

`$ git log --pretty=format:%cd --date=short | uniq | wc -l`

The command that returns the amount of space used by the git directory 

`$ du -h -s .git`

The command that returns the amount of space used by the working directory 

`$ du -h -s --exclude=.git`

The command that produces the number of files in the working directory 

`$ git ls-files | wc -l`

### Restoring revisions with git reset
The history of the repository can be displayed as a list of revisions. We can use `$ git log --pretty=oneline` or the alias `$ git l`. To restore the working directory to one of the revisions you can use: `$ git reset --hard [REVISION]`

### diff between branches
git diff --stat ThisBranch..ThatOtherBranch
### precise merging across branches
git cherry-pick commitHash
cf http://stackoverflow.com/questions/1628563/move-the-most-recent-commits-to-a-new-branch-with-git
### getting back on track from old project
'git for-each-ref --sort=-committerdate refs/heads/'
git checkout lastModifiedBranch
git log -n 5 to find latest 5 commits
git show commitHash to find what was done precisely
### getting a password asked despite having the right SSH keys loaded
instead git clone ssh://myrep instead of git clone https://myrep https://help.github.com/articles/why-is-git-always-asking-for-my-password/
getting error: src refspec master does not match any.
most likely trying to push on the wrong branch, i.e. non master branch
config --glocal color.ui auto to enjoy git diff in color in the terminal
cf http://stackoverflow.com/questions/10998792/how-to-color-the-git-console-in-ubuntu
bare/non-bare
bare repository (as repository/projectname.git/) works with gitweb but still displays no working repository
reset --hard HEAD works but does not sound proper if done after every post-receive (which currently have no effect)
Git bare vs. non-bare repositories by Kim N. Lesmer, bitflop 2010
http://sitaramc.github.com/concepts/bare.html
### wiki integration
moved to Programming#WikiIntegration (part of Programming#ImprovingProcess)
config, rebase, add, commit -a -m "my msg", revert ^HEAD, ...
gitweb
forcing $feature{'highlight'}{'default'} = [1]; in the /etc/gitweb.conf and making the CSS available via push @stylesheets, "http://fabien.benetou.fr/pub/images/repositoryshares/highlight.css";
filter-branch --env-filter "export GIT_AUTHOR_NAME=Fabien Benetou; export GIT_AUTHOR_EMAIL=fabien@benetou.fr" HEAD@@
push over ssh: (especially with ssh-agent running)
clone ssh://user@myserver.tld/path/to/my/repository
gource in the current repository
cf gource, previously added to Programming#VisualizationOfCollaboration
hooks
