# Quality Assurance Parent POM
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
![](https://img.shields.io/badge/Package-JAR-2396ad)
![](https://img.shields.io/badge/Repository-Maven%20Central-2396ad)  
![](https://img.shields.io/badge/JDK-8%20or%20lesser-d6a827)
![](https://github.com/wigforss/java-8-qa-pom/workflows/Test%20and%20Deploy/badge.svg)

Quality Assurance parent POM for Java 8 and lesser projects.

```
<parent>
    <groupId>org.kasource</groupId>
    <artifactId>java-8-qa-pom</artifactId>
    <version>0.3</version>
</parent>
```

Runs QA tools when the system property **run.qa** is set to true.

```
mvn clean verify -Drun.qa=true
```

The following checks and reports are ran when the system property is set or when its profile is activated.

* Checkstyle
* PMD
* Findbugs (JDK < 1.8)
* Spotbugs (JDK > 1.7)
* Cobertura (JDK < 1.8)
* JaCoCo (JDK > 1.7)
* Enforcer
* JavaDoc
* OWASP Dependency Check

Each tool can be enabled individually by setting its profile.

```
mvn clean verify -P checkstyle,pmd,findbugs,spotbugs,cobertura,jacoco,enforcer,javadoc,dependency-check
```

## JDK Version
The default JDK version is 11.

JDK version to use can be specified with the maven property **jdk.version**. Override in child POMs to change JDK version. 

To use JDK 1.8 set the property as
```
 <properties>
     <jdk.version>8</jdk.version>
 </properties>
```