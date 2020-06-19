
 Pi4J V2 :: Java I/O Library for Raspberry Pi :: Minimal example application
==========================================================================

[![Build Status](https://travis-ci.org/Pi4J/pi4j-minimal-example.svg?branch=master)](https://travis-ci.org/Pi4J/pi4j-minimal-example?branch=master) 

This project contains a minimal example application which uses the Pi4J (V2) library and uses a digital output (LED) 
and digital input (push button). Full description is available on [the Pi4J website](https://v2.pi4j.com/getting-started/minimal-example-application)

## PROJECT OVERVIEW

The goal of the example project is to show how to setup a Pi4J Maven project for the Raspberry Pi.

## WIRING

The application needs a LED connected on BCM 22 and button on BCM 24. 

## RUNTIME DEPENDENCIES

This project uses Pi4J V.2 which has the following runtime dependency requirements:
- [**SLF4J (API)**](https://www.slf4j.org/)
- [**SLF4J-SIMPLE**](https://www.slf4j.org/)
- [**PIGPIO Library**](http://abyz.me.uk/rpi/pigpio) (for the Raspberry Pi) - This 
dependency comes pre-installed on recent Raspbian images.  However, you can also 
download and install it yourself using the instructions found 
[here](http://abyz.me.uk/rpi/pigpio/download.html).

## BUILD DEPENDENCIES & INSTRUCTIONS

This project is build using [Apache Maven](https://maven.apache.org/) 3.6 
(or later) and Java 11 OpenJDK (or later).  These prerequisites must be installed 
prior to building this project.  The following command can be used to download 
all project dependencies and compile the Java module.  You can build this 
project directly on a Raspberry Pi with Java 11+.  

```text
mvn clean package
```

Once the build is complete and was successful, you can find the compiled 
artifacts in the `target` folder.  Specifically all dependency modules (JARs)
and a simple `run.sh` bash script will be located in the `target/distribution` 
folder.  These are all the required files needed to distribute (copy) to your
Raspberry Pi to run this project.  If you are using the native bindings running 
locally on the Raspberry Pi, then you make have to run the program using `sudo` 
to gain the necessary access permissions to the hardware I/O.  

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

