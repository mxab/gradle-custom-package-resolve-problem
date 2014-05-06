# Overview

Gradle in version 1.12 tries to resolve custom packages (i.e. .zip) as jars

## Example
### Setup

This package contains to projects
 - bar
 - foo depends on bar (not as a multiproject build but on the bar's uploaded archive)

### Run
 1. Start a local nexus: `./gradlew provideNexus runNexus --no-deamon`
 2. Upload bar package: `./gradlew bar:upload`
 3. Print zip content of foo's dependencies: `./gradlew foo:printAllZipDependenciesContent`
 	you should see the content's of bar's bar.txt
 4. Change the gradle wrapper version to `1.12`
 5. Re run `./gradlew foo:printAllZipDependenciesContent`
 	An error should occure
