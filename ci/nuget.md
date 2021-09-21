# CodeCommit Repo Setup

## Required Files at root of project
These files are required for the CI pipeline to run correctly. They can be copied from an existing project with a CI pipeline. All files will require updates to match the current project name/repourl

* .releaserc
	* Auto version
	* Changelog
	* Update package.json and .csproj version
	* Update git with changes
* Buildspec
	* Sets up the build steps
	* Auth for artifacts
	* Test/Build/Pack/Push
* Package.json
	* Hold important scripts for build process

## CodePipeline Setup
* New pipeline
	* Source/Git/Main/Use full clone
* New build
	* Managed Image/Ubuntu/Standard Runtime/Newest Image
	* Existing Service Role/codebuild-hidive-ci-pipeline-role
* Skip deploy