# DAT250-expass-1
DAT250: Software Technology Experiment Assignment 1

## Part 1: Installation

### Java Development Environment (JDK): oracle.com/java/technologies/javase-downloads.html

1. Checked latest version using supplied link
2. Installed OpenJDK using `brew install openjdk`
3. Ran command as instructed by brew `echo 'export PATH="/opt/homebrew/opt/openjdk/bin:$PATH"' >> ~/.zshrc`
4. Ran `source ~/.zshrc` to refresh CLI
5. Ran `java --version` to verify installation, output:
```
openjdk 17 2021-09-14
OpenJDK Runtime Environment Homebrew (build 17+0)
OpenJDK 64-Bit Server VM Homebrew (build 17+0, mixed mode)
```
 
### An Integrated Development Environment (IDE) which could be Eclipse: eclipse.org/downloads/packages , IntelliJ: jetbrains.com/idea or some other IDE of your choice.

IntelliJ was already installed

### Maven software management tool: maven.apache.org

1. Ran `brew install maven`
2. Ran `mvn --version` to verify installation, output:
```
Apache Maven 3.8.2 (ea98e05a04480131370aa0c110b8c54cf726c06f)
Maven home: /opt/homebrew/Cellar/maven/3.8.2/libexec
Java version: 17, vendor: Homebrew, runtime: /opt/homebrew/Cellar/openjdk/16.0.2/libexec/openjdk.jdk/Contents/Home
Default locale: en_NO, platform encoding: UTF-8
OS name: "***", version: "***", arch: "***", family: "***"

```

### A Git client: git-scm.com

Git was already installed

## Part 2: Experiment: Heroku and Platform as a Service

1. Logged into my Heroku account
2. Started tutorial: devcenter.heroku.com/articles/getting-started-with-java
3. Added autocompletion and logged in 🚀
4. Deployed sample app at: https://guarded-anchorage-32251.herokuapp.com/
5. Built the local app and was able to run it locally as well (ensuring that both java and maven are working)
6. During the step which I was supposed to edit the code, IntelliJ refused to find the installed JDK. I reinstalled it using IntelliJ instead, which solved the issue.
7. Completed the tutorial without any other issues occurring.