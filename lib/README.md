# Apps and libraries used by M.E.T.A.

## eye2.jar

An image recognition java library provided by [https://eyeautomate.com/](https://eyeautomate.com/eye/)

To be used in the M.E.T.A. it needs to be installed into your local maven repository

```
mvn install:install-file -Dfile=eye2.jar -DgroupId=eye -DartifactId=Eye -Dversion=2 -Dpackaging=jar
```

## EyeCapture.jar

EyeCapture is a free image capture tool packed into one small executable Java jar file. The path to the captured image is stored on the clipboard so that you can paste it into the code. The tool is provided by [https://eyeautomate.com/eyecapture/](https://eyeautomate.com/eyecapture/)

Launch it from a terminal window:

```
java -jar EyeCapture.jar
```

## graphwalker-cli-4.2.0.jar

The GraphWalker command line tool. The app is not needed for the workshops, but is provided as a convinience. Read more about the tool here:

* https://github.com/GraphWalker/graphwalker-project/wiki/Command-Line-Tool
* https://github.com/GraphWalker/graphwalker-project/wiki/Offline

## graphwalker-studio-4.2.0.jar

GraphWalker Studio is tool used to create and verify the models created in the M.E.T.A. workshop. Read more about the tool here:
 * https://github.com/GraphWalker/graphwalker-project/wiki/GraphWalker-Studio
 
Launch it from a terminal window:

```
java -jar graphwalker-studio-4.2.0.jar
```

Then start a browser, and enter the url `http://localhost:9090/studio.html`

