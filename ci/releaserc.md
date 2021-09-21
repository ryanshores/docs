document the steps we use here and the options they have
# [Semantic Release](https://github.com/semantic-release/semantic-release)

## Getting started
1. `npm init`
2. add script
3. install devDependencies
4. add .releaserc file (example below)

## package.json

### scripts

-   npx semantic-release

### devDependencies
`npm i -D @semantic-release/changelog @semantic-release/exec @semantic-release/git semantic-release`
-   @semantic-release/changelog
    -   used to generate changelogs
-   @semantic-release/exec
    -   used to run shell command
-   @semantic-release/git
    -   used to push changed to git repo
-   semantic-release
    -   used to updated package version

## .releaserc
```json
{
	"branches": [
            "main"
        ],
	"plugins": [
		"@semantic-release/commit-analyzer",
		"@semantic-release/release-notes-generator",
		"@semantic-release/changelog",
		[
			"@semantic-release/npm",
			{
				"npmPublish": false
			}
		],
		["@semantic-release/exec", {
			"publishCmd": "npm run set-csproj-version"
		}],
		["@semantic-release/git", {
			"assets": ['CHANGELOG.md', 'package.json', 'package-lock.json', 'PATH_TO_CSPROF_FILE|./projectFolder/projectFile.csproj']
		}]
	]
}
```