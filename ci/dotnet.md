# dotnet ci setup

## codebuild 
AWS CodeBuild uses a buildspec.yml file. This should be placed at the root of the project.
Example below:
```yml
version: 0.2

phases:
  install:
    commands:
      - export PATH="$PATH:/root/.dotnet/tools"
      - dotnet tool install -g AWS.CodeArtifact.NuGet.CredentialProvider 
      - dotnet tool install -g dotnet-setversion
      - dotnet codeartifact-creds install
      - npm install --quiet
      - apt-get install jq
  pre_build:
    commands:
      - git config --global credential.helper '!aws codecommit credential-helper $@'
      - git config --global credential.UseHttpPath true
      - dotnet nuget add source -n codeartifact $(aws codeartifact get-repository-endpoint --domain hidive --domain-owner 119302311644 --repository hidive --format nuget --query repositoryEndpoint --output text)"v3/index.json"
  build:
    commands:
      - dotnet build
      - dotnet test
      - npx semantic-release
      - dotnet pack --configuration Release
  post_build:
    commands:
      - dotnet nuget push ./hidive.utilities.datetime/bin/Release/*.nupkg -s codeartifact
```