# About
Concordia's SOEN 345 Lab Project

[🔗Link](https://github.com/rjust/defects4j) to defect4j.

## Team Members

| Name           | Student ID | Email                     |
| -------------- | ---------- | ------------------------- |
| Nathan Grenier | 40250986   | nathangrenier01@gmail.com |

## Pitest Configuration

The following is the Pitest configuration used to generate the mutation test coverage reports with both mutator configs:
```xml
<properties>
    <pitest.version>1.7.3</pitest.version>
</properties>

<plugin>
    <groupId>org.pitest</groupId>
    <artifactId>pitest-maven</artifactId>
    <version>${pitest.version}</version>
    <executions>
        <execution>
        <id>mutation-coverage-all</id>
        <phase>test</phase>
        <goals>
            <goal>mutationCoverage</goal>
        </goals>
        <configuration>
            <mutators>
                <mutator>ALL</mutator>
            </mutators>
            <timestampedReports>true</timestampedReports>
            <reportsDirectory>${project.build.directory}/pit-reports/all</reportsDirectory>
        </configuration>
        </execution>
        <execution>
        <id>mutation-coverage-stronger</id>
        <phase>test</phase>
        <goals>
            <goal>mutationCoverage</goal>
        </goals>
        <configuration>
            <mutators>
            <mutator>STRONGER</mutator>
            </mutators>
            <timestampedReports>true</timestampedReports>
            <reportsDirectory>${project.build.directory}/pit-reports/stronger</reportsDirectory>
        </configuration>
        </execution>
    </executions>
</plugin>
```

# Contributing

## Java Version

Make sure to use java version 11 (11.0.2-oracle).