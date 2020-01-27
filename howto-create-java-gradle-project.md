# Creating a Java Gradle Project

## Installing Gradle

We will be using Gradle 6.1

#### Note: You must have admin privileges to install

Full guide found at https://gradle.org/install/

### Windows

1. Go to https://gradle.org/releases/
1. Download the v6.1 `binary-only` file.
1. Create a new directory `C:\Gradle`
1. Unzip the downloaded binarys and move the contents
into the created `C:\Gradle` directory.
1. In a File Explorer, right-click on `This PC`, then click `Properties` -> `Advanced System Settings` -> `Enviornmental Variables`
1. Under `System Variables` select `Path`, then click `Edit`.
1. Add an entry `C:\Gradle\gradle-6.1\bin` and click OK to save.

### Linux

1. Run the following commands in a terminal:
   - `sudo add-apt-repository ppa:cwchien/gradle`
   - `sudo apt-get update`
   - `sudo apt-get install gradle-6.1`

Verify your installation by opening a **new** terminal \(cmd or
PowerShell for Windows\) and running `gradle --version`

## Creating a Gradle Project

1. In a terminal run the following commands:
   -  `mkdir <project-name>`
   - `cd <project-name>`
   - `gradle init`
1. Select `application` -> `Java` -> `Groovy` -> `JUnit 4`
1. For `Project name` the default option is the name of the directory you are in. You can just press `Enter` if that name is fine.
1. `Source package` MUST be in all lowercase.
1. You can now open the project in your prefered IDE!

## Note:

To run a gradle project with a "normal" terminal for input/output, do the following:
- Add the following to the `build.gradle` file:
```
run {
    standardInput = System.in
}
```
- Run the program using the command `.\gradlew run -q --console=plain` at the project's root directory.