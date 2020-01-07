# Quality Assurance Parent POM
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
![](https://img.shields.io/badge/package-POM-blue)
![](https://img.shields.io/badge/JDK-8%20or%20lesser-d6a827)
![](https://github.com/wigforss/java-8-qa-pom/workflows/Test%20and%20Deploy/badge.svg)

QA parent POM for Java 8 and lesser projects.

Runs QA tools when the system property **run.qa** is set to true.

```
mvn clean verify -Drun.qa=true
```

The following checks and reports are ran when the system property is set or when its profile is activated.

* Checkstyle
* PMD
* Findbugs
* Cobertura
* Enforcer
* JavaDoc
* OWASP Dependency Check

Each tool can be enabled individually by setting its profile.

```
mvn clean verify -P checkstyle,pmd,findbugs,cobertura,enforcer,javadoc,dependency-check
```

## JDK Version
The default JDK version is 8.

*Note:* the JDK version can not be greater than 8. If a later version is required then use [java-11-qa-pom](https://github.com/wigforss/java-11-qa-pom) instead.  

JDK version to use can be specified with the maven property **jdk.version**. Override in child POMs to change JDK version. 

```
 <properties>
     <jdk.version>8</jdk.version>
 </properties>
```