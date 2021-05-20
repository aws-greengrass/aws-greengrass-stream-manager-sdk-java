# AWS Greengrass Stream Manager SDK for Java

The **AWS Greengrass Stream Manager SDK for Java** enables Java developers to manage data streams using [Stream
 Manager](https://docs.aws.amazon.com/greengrass/v2/developerguide/manage-data-streams.html) on AWS IoT Greengrass core.

## Overview

This document provides instructions for preparing your Java code to manage Streams in Stream Manager using the Java SDK.

## Preparing your environment to run Stream Manager

The environment where Stream Manager is running on needs to be able to run Java 8 packages.

*   Install Java 8 for your platform. The method will be different based on your platform.

### Including Stream Manager SDK for Java in your project with Gradle

For this example, you will need to download Gradle. For instructions, go to the gradle website, [https://gradle.org/](https://gradle.org)

Two types of jar files are provided. The `aws-greengrass-stream-manager-sdk-java-slim.jar` in `sdk-slim` directory is a 
jar file with no dependencies built in. This is the recommended way to consume Stream Manager SDK. `aws-greengrass-stream-manager-sdk-java.jar` in
`sdk` directory is provided for backward compatibility for developers already using it.

For `aws-greengrass-stream-manager-sdk-java-slim.jar`, follow the example below:

*   Create `libs` folder.
*   Copy `aws-greengrass-stream-manager-sdk-java-slim.jar` to `libs` folder.
*   Example `build.gradle` file looks like the following. You may add additional dependencies as necessary for your function.  

    ```java  

    repositories {  
        mavenCentral()  
    }  

    dependencies {  
        compile 'com.fasterxml.jackson.core:jackson-annotations:2.12.3'
        compile 'com.fasterxml.jackson.core:jackson-core:2.12.3'
        compile 'com.fasterxml.jackson.core:jackson-databind:2.12.3'
        compile 'com.fasterxml.jackson.dataformat:jackson-dataformat-cbor:2.12.3'
        compile 'javax.validation:validation-api:1.0.0.GA'
        compile 'org.slf4j:slf4j-api:1.7.0'
        compile fileTree(dir: 'libs', include: ['*.jar'])  
    }  

    ```

*   Place your code to consume the SDK under `src` folder.
*   Run `gradle build`

### Using Stream Manager Client to work with Streams

Follow the guide [here](https://docs.aws.amazon.com/greengrass/v2/developerguide/work-with-streams.html) to work
 with Streams using the Stream Manager Client from the Stream Manager SDK.

## Compatibility

Stream Manager SDK provided by this repo is compatible with Stream Manager running on Greengrass Core 1.11 and above.

<div class="Section" id="1.1.0updates">

## 1.1.0 Updates[¶](#1.1.0updates "Permalink to this headline")

Stream manager supports automatic data export to AWS S3 and AWS IoT SiteWise, provides new API method to update existing streams, and pause or resume exporting.

</div>

## Getting Help

*   [Ask on a Greengrass forum](https://forums.aws.amazon.com/forum.jspa?forumID=254)

## License

Apache 2.0