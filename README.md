
 Pi4J V2 :: Java I/O Library for Raspberry Pi :: Minimal example application
==========================================================================

GitHub Actions: 
![Maven build](https://github.com/pi4j/pi4j-example-minimal/workflows/Maven/badge.svg)
![Gradle build](https://github.com/pi4j/pi4j-example-minimal/workflows/Gradle/badge.svg)

This project contains a minimal example application which uses the Pi4J (V2) library and uses a digital output (LED) 
and digital input (push button). Full description is available on [the Pi4J website](https://v2.pi4j.com/getting-started/minimal-example-application)

## PROJECT OVERVIEW

The goal of the example project is to show how to set up a Pi4J Maven / Gradle project for the Raspberry Pi.

## WIRING

The application needs a LED connected on BCM 22 and button on BCM 24. 

![Breadboard schematics used in this example](assets/led-button_bb.png)

## RUNTIME DEPENDENCIES

This project uses Pi4J V.2 which has the following runtime dependency requirements:
- [**SLF4J (API)**](https://www.slf4j.org/)
- [**SLF4J-SIMPLE**](https://www.slf4j.org/)
- [**PIGPIO Library**](http://abyz.me.uk/rpi/pigpio) (for the Raspberry Pi) - This 
dependency comes pre-installed on recent Raspbian images.  However, you can also 
download and install it yourself using the instructions found 
[here](http://abyz.me.uk/rpi/pigpio/download.html).

## BUILD DEPENDENCIES & INSTRUCTIONS

### Maven

This project can be built with [Apache Maven](https://maven.apache.org/) 3.6 
(or later) and Java 11 OpenJDK (or later). These prerequisites must be installed 
prior to building this project.  The following command can be used to download 
all project dependencies and compile the Java module.  You can build this 
project directly on a Raspberry Pi with Java 11+.  

```
mvn clean package
```

### Gradle

You can also use the [Gradle Build Tool](https://gradle.org/) from these same sources. 
Use version 6.6 (or later) and Java 11 OpenJDK (or later). The Gradle wrapper is used as 
described on [docs.gradle.org"](https://docs.gradle.org/current/userguide/gradle_wrapper.html).

On Linux:

```
./gradlew build
```

On Windows:

```
gradlew.bat build
```

### Compiled application to run on the Raspberry Pi

Once the build is complete and was successful, you can find the compiled 
artifacts in the `target` (Maven) or `build` (Gradle) folder.  Specifically 
all dependency modules (JARs) and a simple `run.sh` bash script will be located in the 
`target/distribution` (Maven) or `build/distribution` (Gradle) folder.  

These are all the required files needed to distribute (copy) to your
Raspberry Pi to run this project.  If you are using the native bindings running 
locally on the Raspberry Pi, then you make have to run the program using `sudo` 
to gain the necessary access permissions to the hardware I/O. 

This is the list of files created by the build process of this example application:

* pi4j-core
* pi4j-example-minimal
* pi4j-library-pigpio
* pi4j-plugin-pigpio
* pi4j-plugin-raspberrypi
* slf4j-api
* slf4j-simple
* run.sh --> this is the actual start file which will run pi4j-example-minimal

Make the run script executable and start it like this:

```
chmod +x run.sh
sudo ./run.sh
```

## LICENSE

 Pi4J Version 2.0 and later is licensed under the Apache License,
 Version 2.0 (the "License"); you may not use this file except in
 compliance with the License.  You may obtain a copy of the License at:
      http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.

