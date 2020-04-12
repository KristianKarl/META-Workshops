# WORKSHOP: Model-based Visual GUI Testing

Guides and Instructions for participants

## Introduction

This document describes a workshop on Model-based Visual GUI Testinghosted by the M.E.T.A. project in collaboration with AddQ, Spotify and ArcticBlue. The document contains four sections:

1. **Setup the environment**  - How to setup the environment with Graphwalker, IntelliJ and Eye2.

1. **Create a model** – How to start Graphwalker and create a model

1. **Workshop Assignment** – What to model/automate in the workshop, and how

1. **Questionnaire and contact** – Additional data collection and contact information.

## 1. Setup the environment

### **1.1 Install IntelliJ**

Goto https://www.jetbrains.com/idea/download/ download and install the **Community** version of IntelliJ IDEA.

### **1.2 Install Java 8 from Oracle**

Goto https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html Download and install Java JDK 8 from Oracle.

Graphwalker needs this specific version of java due to the script engine used when executing actions and guards in the models.

### **1.3 Install Maven**

Goto https://maven.apache.org/download.cgi download and install.

### **1.4 Verify the setup**

Open a terminal window and run

```shell
mvn -version
```

You should expect to find the java version and vendor in the output like:

```text
Java version: 1.8.0_201, vendor: Oracle Corporation
```

### **1.5 Clone the META-Workshops GitHub repository**

Open a terminal window and run

```shell
git clone https://github.com/KristianKarl/META-Workshops.git
```

If you don't have `git` get it from here https://git-scm.com/downloads

The change the folder into the repository folder

```shell
cd META-Workshops
```

### **1.6 Install the eye2.jar**

Install the eye2.jar into you local maven repository

```shell
mvn install:install-file -Dfile=lib/eye2.jar -DgroupId=eye -DartifactId=Eye -Dversion=2 -Dpackaging=jar
```

### **1.7 Verify your workshop example project**

Change folder to the provide example project.

```shell
cd projects/exampleProject
```

Then build the example project

```shell
mvn package
```

You should expect

```shell
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

There will be 2 errors showing sayig that GrapwWalker could not find a suitable context factory. You can ignore those errors.

```shell
[ERROR] No suitable context factory found for file: /home/krikar/dev/mbt/meta/github/projects/exampleProject/src/main/resources/img/UbuntuDesktopGuide.png
[ERROR] No suitable context factory found for file: /home/krikar/dev/mbt/meta/github/projects/exampleProject/src/main/resources/img/HelpIcon.png
```

### **1.8 Open the example project in IntelliJ**

Start IntelliJ and import the example project as a Maven project.

When the project is imported, make sure that Java 8 is used as the Projects SDK.

* Open menu `File | Project Structure`

* Under `Project Settings | Project` make sure that **1.8** is selected as the `Project SDK`.

## 2. Create a model

1. In the cloned META-Workshops GitHub repository, open a terminal window and run

   ```shell
   java -jar lib/graphwalker-studio-4.2.0.jar
   ```

1. Open a web-browser and go to the URL: http://localhost:9090/studio.html

1. Create a new model by pressing + and name it by expanding the properties list by clicking on the bottom icon of the bar dark grey bar to the left and changing the property item **Name** to `MySmallTest` (OBS, the naming is important!).

1. Create a vertex by holding down the **v** key and clicking on the model area. See also https://github.com/GraphWalker/graphwalker-project/wiki/GraphWalker-Studio

1. Connect two vertexes with an edge by pressing **e** and dragging and dropping between the vertexes. See also https://github.com/GraphWalker/graphwalker-project/wiki/GraphWalker-Studio

1. Rename vertexes/edges by clicking on them and naming it in the properties list (left side bar)

1. Select one vertex and make it a start element by toggling `Start element` in the properties list (bottom of the list). OBS! Preferably this node is not part of the modelled scenario.

1. Run the model with the `play` button. All model elements should turn green if it works.

1. Save the model in the example project as `projects/exampleProject/src/main/resources/com/company//MySmallTest.json` (Note, the location is important).

1. Open the project in IntelliJ, expand the Maven bar to the right in IntelliJ and then expand: `META Workshop example project/Plugins/graphwalker` and run `graphwalker:generate-sources`.

1. Open the Java class `SomeSmallTest` located in the project hierarchy under `src/main/java/com.company/`.

    Change the interface that the `class SomeSamllTest` should from:

    ```java
    public class SomeSmallTest extends ExecutionContext implements SmallTest
    ```

    to

    ```java
    public class SomeSmallTest extends ExecutionContext implements MySmallTest
    ```

    Comment out all methods with the annotation `@Override`.

    Hover over the class definition and choose `Implement methods`.

1. Run the test using the `main` method in the class `com.compan.Runner`.

## 3. Workshop Assignment

In the workshop, you will work individually to automate tests for the following five user stories.

* **Feature 1:** As a veterinarian, I want to search for pet owners by their last name to quickly find owners associated with the PetClinic service.

* **Feature 2:** As a user, I want to register owners by First Name, Last Name, Address, City and Telephone number.

* **Feature 3:** As a pet owner, I want to sort the list of available veterinarians based on different attributes (name/speciality).

* **Feature 4:** As a pet owner, I want to search for veterinarians based on name and last name to quickly see them.

* **Feature 5:** As a pet owner, I want to add pets to my profile.

For each story, starting with Feature 1, you should do the following:

1. Open Graphwalker and create a model for the feature’s behavior

1. Save the model, update the Java interface and create interaction code for your model in IntelliJ

1. Document the development time of the model and code.

1. Continue with Feature 2, then Feature 3, etc.

Document the requested information about your modelling/coding progress in the following google form:
https://docs.google.com/forms/d/e/1FAIpQLSdHZdLrBfQirnrGhAhhJ8mLljwyHuVC6UjlQ0v4MrSmYyqZqQ/viewform?usp=sf_link

The user stories relate to a web-service called PetClinic that will be used in the workshop for MBT, where you will develop and maintain the models/test code as follows:

1. Open a terminal window and from the root of the `META-Workshops` folder, change to the folder of PetClinic_v1

    ```shell
    cd petclinic/PetClinic_v1
    ```

1. Start PetClinic version 1

    ```shell
    java –jar petclinic_v1.jar
    ```

1. Open your web browser and input the URL: http://localhost:9966/petclinic/. This should open the PetClinic homepage.

1. Create a model(s) and interaction code for the features presented above. Make sure to record the time spent and other requested metrics for the development in the google form.

1. Shutdown version 1 of PetClinic by pressing `Ctrl+c` in the terminal window of step 2.

1. Change to the folder of PetClinic_v2 (from the root  of the `META-Workshops` folder)

    ```shell
    cd petclinic/PetClinic_v2
    ```

1. Start PetClinic version 2

    ```shell
    java –jar petclinic_v2.jar
    ```

1. Run the tests created for **PetClinic_v1** and note any changes and update/maintain the test cases until they work again. Make sure to record the time spent and other requested metrics for the maintenance in the google form.

## 4. Questionnaire and contact

As a final step of the workshop, fill in the questionnaire in the end of the google form that you have used to document development time of models and code. If you have any questions before, during or after the workshop, feel free to contact Dr. Emil Alégroth emil.alegroth@bth.se or +46 (0)703-338022.

THANK YOU FOR YOUR PARTICIPATION
