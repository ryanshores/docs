# Introduction

When using AWS CodePipeline with Semantic Release there exists an issue with the commit that is created when making a new version. SR analyzes the commits that have occures since the last tagged release, and determines the type on version to increment. Upon doing this a changelog entry is make, and the version is updated. This is commited and pushed, and the build continues on with the new version.

This new commit will retrigger the build and since there are no changes no new version is required and the build fails. This means there will be one bad build following every successful build.

To remedy this issue a custom lambda has been created. The Code Pipeline trigger is updated to point to the lambda rather than the build, and the lambda determines wether the build pipeline should continue. It is setup to look for the [skip-ci] tag that SM appends to the commit message. 

## Setup

After creating the default code pipeline, and having at least one run go to the history in the AWS Console. Click on the trigger and follow to the rule that starts the pipeline. This will need to be edited to point to the lambda instead. 

Note the rule name under history. It has a unique number that can be used to search for the rule in Amazon EventBridge Rules. 

Edit and go to the `Select targets` section. Select `Target => Lambda Function => hidive-ci-deploy-stack` 

Set Values:
* **Target**: *Lambda Function* 
* **Function**: *hidive-ci-deploy-stack*
* **Alias**: *current*