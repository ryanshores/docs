# Introduction

Code artifact is a private repository aws service. It allows us to track the package versions used in our projects, and to publish private packages. Code artifact can work with several package management services (npm/nugat/etc).

## Authentication

``` 
dotnet tool install -g AWS.CodeArtifact.NuGet.CredentialProvider
dotnet codeartifact-creds install
dotnet codeartifact-creds configure set profile [named-aws-cli-profile]
```

[Docs](https://docs.aws.amazon.com/codeartifact/latest/ug/nuget-cli.html)

## Terms

* Domain
  * Used to manage access on at organization level
  * Ex. HIDIVE
* Repository
  * A place where different installable packages are maintained with versioning
  * Ex. NPM, Nugat
* Versioning
  * A build of a package
  * Ex. 1.2.3.4

### External Sources

[AWS Code Artifact](https://aws.amazon.com/codeartifact/)

## Uses

The primary use for us will be to host our private packages. Artifact will allow internal libraries to be published and shared in a versioned manor. This will solve the issues of not-often-used apps needing to be updated to the current projects, even if they do not require the changes.

This is also where I am proposing we host the hidive-ui project that I hope will become a global source of react components for hidive. Apps will be able to install the hidive-ui package from our artifact repo and reuse already approved components.

By utilizing the versioning control we would be able to implement CI for the hidive-ui package as the package will not be immediately published to apps using the UI, but rather they would get the update the next time the app get’s deployed.

In addition with nugat packages we can start to build C# libraries that can be used for better project separation into different solutions.
