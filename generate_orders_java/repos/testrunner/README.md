# Test Runner

This plugin allows you to create tools that operate on Java (JUnit) tests with fine-grained control (e.g., running them in arbitrary orders).
This code was originally from https://github.com/ReedOei/testrunner, all development has been moved to here.

# Quickstart

First, create a class that extends the following abstract class:

```java
public abstract class TestPlugin {
    public TestPlugin() {}

    public abstract void execute(final ProjectWrapper project);
}
```

Then, add the following plugin to the `pom.xml` of the Maven project you wish to run your `TestPlugin` on.

```xml
<plugin>
    <groupId>edu.illinois.cs</groupId>
    <artifactId>testrunner-maven-plugin</artifactId>
    <version>1.2</version>
    <configuration>
        <className>FULLY_QUALIFIED_CLASS_NAME_GOES_HERE</className>
    </configuration>
</plugin>
```

Then run:

```
mvn testrunner:testplugin
```

# Installation

If you want the latest version of this plugin (or for some reason you can't get if off Maven central), you can run:

```bash
git clone https://github.com/TestingResearchIllinois/testrunner
cd testrunner
mvn install
```

and change the plugin version to the latest one (currently 1.3-SNAPSHOT)

You can generate documentation using:
```
mvn javadoc:javadoc
```
# Documentation

See the [wiki](https://github.com/TestingResearchIllinois/testrunner/wiki).
