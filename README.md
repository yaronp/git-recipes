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
The history of the repository can be displayed as a list of revisions. We can use $ git log --pretty=oneline or the alias $ git l. As you already know, every revision is identified by its unique name. To restore the working directory to one of the revisions you can use:

` git reset --hard [REVISION]`
