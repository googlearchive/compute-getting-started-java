compute-getting-started-java
============================

This sample command line application demonstrates how to access the Google
Compute Engine API using the Google Java API Client Library.

## Products
 - [Compute Engine][https://developers.google.com/compute]

## Language
 - [Java][http://java.com]

## APIs
 - [Google Compute Engine][https://developers.google.com/compute]

## Setup Instructions
1. Register your application with Google Cloud Console.
    1. Visit the [Cloud Console][http://cloud.google.com/console]
    1. If this is your first time then click "Create Project," otherwise you can
reuse an existing project by click on it.
        1. Note: You will need to enable billing for new projects by clicking
on Compute Engine in the left hand navigation menu.
    1. Click on "APIs & auth" in the left hand navigation menu and then the
"Registered Apps" subitem.
    1. Click on "Register App," enter "GCE Sample," as the name, choose the
"Native" type and click the "Register," button.
    1. Expand the "OAuth 2.0 Client ID" section of the screen and download the
JSON file using the button supplied. Later on you will copy this downloaded
file (`e.g. ~/Downloads/client_secrets.json`) to
[`src/main/resources/client_secrets.json`][https://www.github.com/GoogleCloudPlatform/compute-getting-started-java/master/src/main/resources/client_secrets.json].
    1. Click Overview in the left hand navigation and copy your Project ID
into into
[`/src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java`][https://www.github.com/GoogleCloudPlatform/compute-getting-started-java/master/src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java]
so that the line
`private static final String projectId = "YOUR_PROJECT_ID"`
is updated. Not performing this step will result in an 400: Bad Request error;
specifically, "Invalid value 'YOUR_PROJECT_ID'.". For more information see
setting your
[Project ID][https://developers.google.com/console/help/#projectid].

1. Code Checkout Instructions
    1. Pre-requisites: install [Java 6][http://java.com/],
[Git][http://git-scm.com/downloads], and
[Maven][http://maven.apache.org/download.html]. You may need to set your
`JAVA_HOME` environment variable as well.
    1. Download code:
`cd <some_directory>
git clone https://github.com/GoogleCloudPlatform/compute-getting-started-java.git 
cd compute-getting-started-java
cp ~/Downloads/client_secrets.json src/main/resources/client_secrets.json
[any_editor_but_preferably_vi] src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java`
In your editor update the 'YOUR_PROJECT_ID' value as specified above. Save and
exit the editor.
    1. Compile code using Maven using the following command
`mvn compile`
    1. Execute code using Maven using the following command
`mvn -q exec:java`

1. Importing the code into Eclipse and running it from there
    1. Prerequisites: install [Eclipse][http://www.eclipse.org/downloads/]
and the
[Maven plugin for Eclipse][http://m2eclipse.sonatype.org/installing-m2eclipse.html].
    1. Download code as specified above.
    1. File -> Import -> Maven -> Existing Maven Projects -> Next.
    1. Select your project directory as your "Root Directory," and click
"Finish."
    1. Right-click on project compute-engine-cmdline-sample
    1. Run As > Java Application
    1. If asked, type "ComputeEngineSample" and click OK
    1. Application output will display in the Console.
