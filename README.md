# git-recipes
## Common GIT Recipes

### Analyzing a repository with git log and shortlog commands

* The command that prints the number of commits in the repository

`bash $ git log --pretty=oneline | wc -l`

The command that prints the number of contributors

`$ git shortlog -s | wc -l`
