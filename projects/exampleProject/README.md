# Example project for M.E.T.A.

## Setup

Make sure to follow the instructions in this [README.md](../../README.md)

## Verify the example project environment

From the command line, run:

```
mvn package
```

You should expect

```
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

There will be 2 errors showing sayig that GrapwWalker could not find a suitable context factory. You can ignore those errors.

```
[ERROR] No suitable context factory found for file: /home/krikar/dev/mbt/meta/github/projects/exampleProject/src/main/resources/img/UbuntuDesktopGuide.png
[ERROR] No suitable context factory found for file: /home/krikar/dev/mbt/meta/github/projects/exampleProject/src/main/resources/img/HelpIcon.png
```
