# cloudformation-github

## Set up git filter

This project uses a filter set up in the [.gitattributes](.gitattributes) file to replace private values for testing within the different `overides.json` on each resource.

The filter has to be added manually inside the `.git/config` file once the repository has been cloned.

Executing this in the console from the project root will add it. Replace the values inside the __square__ brackets with the actual values for testing

```properties
cat << EOF >> .git/config
[filter "github-token"]
	clean = sed \\
		-e 's:[githubAccessToken]:<GITHUB_TOKEN>:g' \\
		-e 's:[organizacionForTesting]:<GITHUB_ORG>:g' \\
		-e 's:[existingTeamForTesting]:<GITHUB_TEAM>:g' \\
		-e 's:[existingGithubUserForTesting]:<GITHUB_USERNAME>:g' 
	smudge = sed \\
		-e 's:<GITHUB_TOKEN>:[githubAccessToken]:g' \\
		-e 's:<GITHUB_ORG>:[organizacionForTesting]:g' \\
		-e 's:<GITHUB_TEAM>:[existingTeamForTesting]:g' \\
		-e 's:<GITHUB_USERNAME>:[existingGithubUserForTesting]:g'
EOF
```