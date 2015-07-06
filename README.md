compute-getting-started-java
============================

This sample command line application demonstrates how to access the Google
Compute Engine API using the Google Java API Client Library.

## Products
- [Compute Engine][1]

## Language
- [Java][2]

## APIs
- [Google Compute Engine][3]

## Setup Instructions
1. Register your application with Google Cloud Console.
  1. Visit the [Cloud Console][4]
  1. If this is your first time then click "Create Project," otherwise you can
reuse an existing project by clicking on it.
    1. Note: You will need to enable billing for new projects by clicking
on Compute Engine in the left hand navigation menu.
  1. Click on "APIs & auth" in the left hand navigation menu and then the
"Registered Apps" subitem.
  1. Click on "Register App," enter "GCE Sample," as the name, choose the
"Native" type and click the "Register," button.
  1. Expand the "OAuth 2.0 Client ID" section of the screen and download the
JSON file using the button supplied. Later on you will copy this downloaded
file to [`src/main/resources/client_secrets.json`][5].
  1. Click "Overview" in the left hand navigation and copy your Project ID into into [`/src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java`][6]
so that the following line is updated. Not performing this step will result in an 400: Bad Request error;
specifically, "Invalid value `YOUR_PROJECT_ID`". For more information see
setting your [Project ID][7].
<pre>private static final String projectId = "YOUR_PROJECT_ID"`</pre>
1. Code Checkout Instructions
  1. Pre-requisites: install [Java 6][2], [Git][8], and [Maven][9].
You may need to set your
`JAVA_HOME` environment variable as well.
  1. Download code:
<pre>
cd some_directory
git clone https://github.com/GoogleCloudPlatform/compute-getting-started-java.git
cd compute-getting-started-java
cp ~/Downloads/client_secret_[id-unique-to-your-project-application].json src/main/resources/client_secrets.json
nano src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java</pre>
  1. In your editor update the `YOUR_PROJECT_ID` value as specified above. Save and exit the editor.
  1. Compile code using Maven using the following command:
<pre>mvn compile</pre>
  1. Execute code using Maven via the following command:
<pre>mvn -q exec:java</pre>
1. Import the code into Eclipse and running it from there
  1. Prerequisites: install [Eclipse][10] and the [Maven plugin for Eclipse][11].
  1. Download code as specified above.
  1. File -> Import -> Maven -> Existing Maven Projects -> Next.
  1. Select your project directory as your "Root Directory," and click "Finish."
  1. Right-click on project compute-engine-cmdline-sample
  1. Run As > Java Application
  1. If asked, type "ComputeEngineSample" and click OK
  1. Application output will display in the Console.
 
[1]: https://developers.google.com/compute
[2]: http://java.com
[3]: https://developers.google.com/compute
[4]: http://cloud.google.com/console
[5]: https://github.com/GoogleCloudPlatform/compute-getting-started-java/blob/master/src/main/resources/client_secrets.json
[6]: https://github.com/GoogleCloudPlatform/compute-getting-started-java/blob/master/src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java#L51
[7]: https://developers.google.com/console/help/#projectid
[8]: http://git-scm.com/downloads
[9]: http://maven.apache.org/download.html
[10]: http://www.eclipse.org/downloads/
[11]: http://eclipse.org/m2e/download/
