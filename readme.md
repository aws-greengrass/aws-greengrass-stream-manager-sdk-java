# AWS Greengrass Stream Manager SDK for Java

The **AWS Greengrass Stream Manager SDK for Java** enables Java developers to manage data streams using [Stream
 Manager](https://docs.aws.amazon.com/greengrass/latest/developerguide/stream-manager.html) on AWS IoT Greengrass core.

## Overview

This document provides instructions for preparing your Java code to manage Streams in Stream Manager using the Java SDK.

## Preparing your environment to run Stream Manager

The environment where Stream Manager is running on needs to be able to run Java 8 packages.

*   Install Java 8 for your platform. The method will be different based on your platform.

### Including Stream Manager SDK for Java in your project with Gradle

For this example, you will need to download Gradle. For instructions, go to the gradle website, [https://gradle.org/](https://gradle.org)

Follow the steps below.

*   Create `libs` folder.
*   Copy `aws-greengrass-stream-manager-sdk-java.jar` to `libs` folder.
*   Example `build.gradle` file looks like the following. You may add additional dependencies as necessary for your function.  

    ```java  

    repositories {  
        mavenCentral()  
    }  

    dependencies {  
        compile 'com.fasterxml.jackson.core:jackson-core:2.8.8'  
        compile 'com.fasterxml.jackson.core:jackson-databind:2.8.8'  
        compile 'org.apache.httpcomponents:httpclient:4.5.3'  
        compile 'com.amazonaws:aws-lambda-java-core:1.1.0'  
        compile 'com.amazonaws:aws-java-sdk-core:1.11.178'  
        compile fileTree(dir: 'libs', include: ['*.jar'])  
    }  

    ```

*   Place your code to consume the SDK under `src` folder.
*   Run `gradle build`

### Using Stream Manager Client to work with Streams

Follow the guide [here](https://docs.aws.amazon.com/greengrass/latest/developerguide/work-with-streams.html) to work
 with Streams using the Stream Manager Client from the Stream Manager SDK.

## Compatibility

Stream Manager SDK provided by this repo is compatible with Stream Manager running on Greengrass Core 1.11 and above.
