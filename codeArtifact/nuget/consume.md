# Nuget Consuming

## Introduction

In order to consume private packages from our AWS artifacts server you will need to add our artifact endpoint to the nuget package sources.

## Quick Start

* Authenticate dotnet tools
  * for instructions see sister article dotnet cli authenticate
* retrieve the artifact endpoint
  * AWS Explorer → CodeArtifact → hidive → hidive → right click
* Add as package source
  * Tools → Options → Nuget Package Manager → Package Sources
* When installing change the source to all or hidive

## Setup

For detailed instructions on setting up nuget package manager in visual studio see the [AWS documentation](https://docs.aws.amazon.com/codeartifact/latest/ug/nuget-visual-studio.html)

### Troubleshooting

* Unable to find package when installing new version
  * Nuget cache needs to be reset
    * Tools → Options → Nuget Package Manager → Clear All Nuget Cache(s)
