# M.E.T.A. example projects

This repository contains all the files, folders and structure needed to get started with the M.E.T.A. workshops during 2020.

## Verify your development environment

You need to use Java 8 from Oracle. To verify, run:

```
mvn -version
```

You should expect to find the java version and vendor in the output like:

```
Java version: 1.8.0_201, vendor: Oracle Corporation
```

## Install the eye2.jar into you local maven repository

```
mvn install:install-file -Dfile=lib/eye2.jar -DgroupId=eye -DartifactId=Eye -Dversion=2 -Dpackaging=jar
```
