### Out of 10 points

### Enforced by the checkpoint test suite (suite present and passing = full points):

2 - Pull Request that failed the status checks

2 - Pull Request that now passes the status checks

1 - checkstyle.yml and gradle.yml configured properly

2 - checkstyle.xml and build.gradle configured properly


### Other:
1 - Branch protection rules; get the point unless missing 2 or more of:
	- correct status checks (both)
	- rules enabled
	- rules apply to main branch

2 - additional checkstyle rule (must have a non-default commit message plus the rule, 1 point each)

### Important Notes:
After checkpoint 1, folks should disable the checkpoint 1 suite so they don't run into rate limiting issues with the github API free tier