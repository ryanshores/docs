# Publishing Sentai

## Dev/Qa 
1. Update S3 with new files
2. Push new theme
3. enable password
   1. could this be accomplished with a cli?
4. deploy theme to live theme
5. Push to beanstalk
6. disable password

**Prebuild**
* extract the version from project
* move to shopify theme

**S3 Publish**
cp [content/*, scripts/*] s3://{version}/{env}/[styles,scripts]

**Push New Shopify Theme**
1. yarn {env}-push-theme -n v{version}

