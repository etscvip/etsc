# Welcome to ETSCeumj

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ETSCeum/ETSCeumj?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/ETSCeum/ETSCeumj.svg?branch=master)](https://travis-ci.org/ETSCeum/ETSCeumj)
[![Coverage Status](https://coveralls.io/repos/ETSCeum/ETSCeumj/badge.png?branch=master)](https://coveralls.io/r/ETSCeum/ETSCeumj?branch=master)


# About
ETSCeumJ is a pure-Java implementation of the ETSCeum protocol. For high-level information about ETSCeum and its goals, visit [ETSCeum.org](https://ETSCeum.org). The [ETSCeum white paper](https://github.com/ETSCeum/wiki/wiki/White-Paper) provides a complete conceptual overview, and the [yellow paper](http://gavwood.com/Paper.pdf) provides a formal definition of the protocol.

We keep ETSCeumJ as thin as possible. For [JSON-RPC](https://github.com/ETSCeum/wiki/wiki/JSON-RPC) support and other client features check [ETSCeum Harmony](https://github.com/ETSC-camp/ETSCeum-harmony).

# Running ETSCeumJ

##### Adding as a dependency to your Maven project: 

```
   <dependency>
     <groupId>org.ETSCeum</groupId>
     <artifactId>ETSCeumj-core</artifactId>
     <version>1.8.0-RELEASE</version>
   </dependency>
```

##### or your Gradle project: 

```
   repositories {
       mavenCentral()
       jcenter()
       maven { url "https://dl.bintray.com/ETSCeum/maven/" }
   }
   compile "org.ETSCeum:ETSCeumj-core:1.8.+"
```

As a starting point for your own project take a look at https://github.com/ETSC-camp/ETSCeumj.starter

##### Building an executable JAR
```
git clone https://github.com/ETSCeum/ETSCeumj
cd ETSCeumj
cp ETSCeumj-core/src/main/resources/ETSCeumj.conf ETSCeumj-core/src/main/resources/user.conf
vim ETSCeumj-core/src/main/resources/user.conf # adjust user.conf to your needs
./gradlew clean fatJar
java -jar ETSCeumj-core/build/libs/ETSCeumj-core-*-all.jar
```

##### Running from command line:
```
> git clone https://github.com/ETSCeum/ETSCeumj
> cd ETSCeumj
> ./gradlew run [-PmainClass=<sample class>]
```

##### Optional samples to try:
```
./gradlew run -PmainClass=org.ETSCeum.samples.BasicSample
./gradlew run -PmainClass=org.ETSCeum.samples.FollowAccount
./gradlew run -PmainClass=org.ETSCeum.samples.PendingStateSample
./gradlew run -PmainClass=org.ETSCeum.samples.PriceFeedSample
./gradlew run -PmainClass=org.ETSCeum.samples.PrivateMinerSample
./gradlew run -PmainClass=org.ETSCeum.samples.TestNetSample
./gradlew run -PmainClass=org.ETSCeum.samples.TransactionBomb
```

##### Importing project to IntelliJ IDEA: 
```
> git clone https://github.com/ETSCeum/ETSCeumj
> cd ETSCeumj
> gradlew build
```
  IDEA: 
* File -> New -> Project from existing sources…
* Select ETSCeumj/build.gradle
* Dialog “Import Project from gradle”: press “OK”
* After building run either `org.ETSCeum.Start`, one of `org.ETSCeum.samples.*` or create your own main. 

# Configuring ETSCeumJ

For reference on all existing options, their description and defaults you may refer to the default config `ETSCeumj.conf` (you may find it in either the library jar or in the source tree `ETSCeum-core/src/main/resources`) 
To override needed options you may use one of the following ways: 
* put your options to the `<working dir>/config/ETSCeumj.conf` file
* put `user.conf` to the root of your classpath (as a resource) 
* put your options to any file and supply it via `-DETSCeumj.conf.file=<your config>`
* programmatically by using `SystemProperties.CONFIG.override*()`
* programmatically using by overriding Spring `SystemProperties` bean 

Note that don’t need to put all the options to your custom config, just those you want to override. 

# Special thanks
YourKit for providing us with their nice profiler absolutely for free.

YourKit supports open source projects with its full-featured Java Profiler.
YourKit, LLC is the creator of <a href="https://www.yourkit.com/java/profiler/">YourKit Java Profiler</a>
and <a href="https://www.yourkit.com/.net/profiler/">YourKit .NET Profiler</a>,
innovative and intelligent tools for profiling Java and .NET applications.

![YourKit Logo](https://www.yourkit.com/images/yklogo.png)

# Contact
Chat with us via [Gitter](https://gitter.im/ETSCeum/ETSCeumj)

# License
ETSCeumj is released under the [LGPL-V3 license](LICENSE).

