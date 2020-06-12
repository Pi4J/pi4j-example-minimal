
 Pi4J V2 :: Java I/O Library for Raspberry Pi :: Minimal example application
==========================================================================

[![Build Status](https://travis-ci.org/Pi4J/pi4j-minimal-example.svg?branch=master)](https://travis-ci.org/Pi4J/pi4j-minimal-example?branch=master) 

This project contains a minimal example application which uses the Pi4J (V2) library and uses a digital output (LED) 
and digital input (push button).

---

## DISCLAIMER:: EXPERIMENTAL VERSION

### This repository is an experimental and incomplete work-in-progress for the next major version of Pi4J.

### !! NOT READY FOR PRODUCTION USE !!

---

## PROJECT INFORMATION

Project website: https://pi4j.com/ <br />
Pi4J Community Forum (*new*): https://forum.pi4j.com/ <br />
Version 2.0 Project Discussions (*new*): https://forum.pi4j.com/category/6/version-2-0 <br />

Copyright (C) 2012-2020 Pi4J

## PROJECT OVERVIEW

The goal of the example project is to show how to setup a Pi4J Maven project for the Raspberry Pi.

## RUNTIME DEPENDENCIES

This project used Pi4J V.2 which has the following runtime dependency requirements:
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
project on you workstation or directly on a Raspberry Pi.  

```text
mvn clean install
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

## IN DEVELOPMENT

* 2020-06-11 :: Start of this project

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

