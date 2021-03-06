https://github.com/libgdx/libgdx/wiki

### Prerequisites

* JDK 7+
* Eclipse/IntelliJ
* Android SDK
* ADT for Eclipse
* Eclipse Gradle plugin
* RoboVM Plugin (for iOS)

### Setting up the Development Environment

https://github.com/libgdx/libgdx/wiki/Setting-up-your-Development-Environment-%28Eclipse%2C-Intellij-IDEA%2C-NetBeans%29

### Creating a project Using the Gradle-based setup

https://github.com/libgdx/libgdx/wiki/Project-Setup-Gradle

Download gdx-setup.jar (https://libgdx.badlogicgames.com/download.html)

Downloaded to ~/software/libGDX directory

> software//LibGDX$ java -jar gdx-setup.jar

    Exception in thread "main" java.awt.HeadlessException
    	at java.awt.GraphicsEnvironment.checkHeadless(GraphicsEnvironment.java:207)
    	at java.awt.Window.<init>(Window.java:535)
    	at java.awt.Frame.<init>(Frame.java:420)
    	at java.awt.Frame.<init>(Frame.java:385)
    	at javax.swing.JFrame.<init>(JFrame.java:174)
    	at com.badlogic.gdx.setup.GdxSetupUI.<init>(Unknown Source)
    	at com.badlogic.gdx.setup.GdxSetup.main(Unknown Source)

Resolving the problem ... 

The JAVA_HOME path variable is pointing to Java 8 SDK, but the java command on the system refers to the OpenJDK JRE.

    software$ java -version 
    java version "1.7.0_95"
    OpenJDK Runtime Environment (IcedTea 2.6.4) (7u95-2.6.4-0ubuntu0.14.04.1)
    OpenJDK 64-Bit Server VM (build 24.95-b01, mixed mode)
    droid@droidserver:~/software/LibGDX$ java -version 
    java version "1.7.0_95"
    OpenJDK Runtime Environment (IcedTea 2.6.4) (7u95-2.6.4-0ubuntu0.14.04.1)
    OpenJDK 64-Bit Server VM (build 24.95-b01, mixed mode)
    droid@droidserver:~/software/LibGDX$ which java
    /usr/bin/java
    droid@droidserver:~/software/LibGDX$ ls -l /usr/bin/java
    lrwxrwxrwx 1 root root 22 Feb 13 14:52 /usr/bin/java -> /etc/alternatives/java
    droid@droidserver:~/software/LibGDX$ ls -l /etc/alternatives/java
    lrwxrwxrwx 1 root root 46 Feb 13 14:52 /etc/alternatives/java -> /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java
    droid@droidserver:~/software/LibGDX$ echo $JAVA_HOME
    /home/droid/software/java/jdk1.8.0_65
    droid@droidserver:~/software/LibGDX$ cd $JAVA_HOME
    droid@droidserver:~/software/java/jdk1.8.0_65$ ls
    bin        db     include         jre  LICENSE  README.html  src.zip                             THIRDPARTYLICENSEREADME.txt
    COPYRIGHT  demos  javafx-src.zip  lib  man      release      THIRDPARTYLICENSEREADME-JAVAFX.txt
    droid@droidserver:~/software/java/jdk1.8.0_65$ cd bin
    droid@droidserver:~/software/java/jdk1.8.0_65/bin$ find java
    java
    droid@droidserver:~/software$ /home/droid/software/java/jdk1.8.0_65/bin/java -version
    java version "1.8.0_65"
    Java(TM) SE Runtime Environment (build 1.8.0_65-b17)
    Java HotSpot(TM) 64-Bit Server VM (build 25.65-b01, mixed mode)

Using Java version 1.8 opens up the LibGDX's project creation wizard.

    droid@droidserver:~/software/LibGDX$ /home/droid/software/java/jdk1.8.0_65/bin/java -jar gdx-setup.jar 
    Usage: GdxSetup --dir <dir-name> --name <app-name> --package <package> --mainClass <mainClass> --sdkLocation <SDKLocation>
    dir ... the directory to write the project files to
    name ... the name of the application
    package ... the Java package name of the application
    mainClass ... the name of your main ApplicationListener
    sdkLocation ... the location of your android SDK. Uses ANDROID_HOME if not specified

<img src="_misc/libGDX%20project%20creation%20UI.png"/>

### Pointing to Java 8

    droid@droidserver:~/software/LibGDX$ sudo update-alternatives --install "/usr/bin/java" "java" "/home/droid/software/java/jdk1.8.0_65/bin/java" 1
    droid@droidserver:~/software/LibGDX$ sudo update-alternatives --remove "java" "/usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java"
    update-alternatives: using /home/droid/software/java/jdk1.8.0_65/bin/java to provide /usr/bin/java (java) in auto mode
    droid@droidserver:~/software/LibGDX$ which java
    /usr/bin/java
    droid@droidserver:~/software/LibGDX$ java -version
    java version "1.8.0_65"
    Java(TM) SE Runtime Environment (build 1.8.0_65-b17)
    Java HotSpot(TM) 64-Bit Server VM (build 25.65-b01, mixed mode)

Now, the java command can be used directly without having to specify the whole path. The following opens up the Project Creation Wizard.

> software/LibGDX$ java -jar gdx-setup.jar 

### Creating a Project to be imported in Eclipse

<img src="_misc/Create%20a%20sample%20project.png"/>

Click Advanced, Select Eclipse and Hit Save

<img src="_misc/Select%20Eclipse.png"/>

Click Generate and wait ...

<img src="_misc/After%20Project%20Creation.png"/>

<b> Files Generated </b>

> scratchpad/LibGDX$ ls Sample/

    android  build.gradle  core  desktop  gradle  gradle.properties  gradlew  gradlew.bat  html  ios  local.properties  settings.gradle

### Import Project to Eclipse

<b> Import the project to eclipse </b>

<img src="_misc/Import%20a%20Gradle%20Project.png"/>

<b> Build the Project </b>

Click "Build Model"

<img src="_misc/Build%20Model.png"/>

Choose the generated folders and click finish

<img src="_misc/After%20Project%20is%20Built.png"/>

### Project Structure and Contents

<img src="_misc/Project%20Structure.png"/>

<img src="_misc/Project%20structure%20-%20android.png"/>

<img src="_misc/Project%20Structure%20-%20Core.png"/>

<img src="_misc/Project%20Structure%20-%20Desktop.png"/>

<img src="_misc/Project%20Structure%20-%20Html.png"/>

<img src="_misc/Project%20Structure%20-%20iOS.png"/>

<img src="_misc/Project%20Structure%20-%20Sample.png"/>

### Understanding Contents

