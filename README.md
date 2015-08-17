compute-getting-started-java
============================

This sample command line application demonstrates how to access the Google
Compute Engine API using the Google Java API Client Library.

When the sample is setup and run as instructed below, it will list all the
VM instances in a Google Cloud Platform project for a specific
[zone](https://cloud.google.com/compute/docs/zones).
The sample also checks for the existence of a VM instance named
"my-sample-instance". If the VM instance doesn't exist, the sample
will create a new VM instance named "my-sample-instance". If the VM instance
does exist, running the sample will delete the instance. The instance create
and delete actions are implemented as
"[zone specific operations](https://cloud.google.com/compute/docs/reference/latest/zoneOperations#resource)".
The sample demonstrates how to poll the status of these operations to
determine when and if they successfully complete.

## Products
- [Compute Engine][1]

## Language
- [Java][2]

## APIs
- [Google Compute Engine][3]

## Setup Instructions
1. Create or select a project in the Google Developers Console:
  1. Visit the [Developers Console][4]
  1. If this is your first time then click "Create Project," otherwise you can
reuse an existing project by clicking on it.
    1. Note: You will need to enable billing for the project to use Compute
    Engine.
  1. Click "Overview" in the left-side navigation menu and copy your Project ID
  for use in step 3.3 below.

1. Authentication instructions to run the sample:
  * Running the sample locally on your development machine:
      1. Install [Google Cloud SDK](https://cloud.google.com/sdk/)
      1. Run the following command to authenticate with your own account:
      <pre>gcloud auth login</pre>
  * Running the sample on Google Compute Engine using Default Application
  Credentials:
      1. Create a Compute Engine VM Instance.
      1. In the [Developers Console](https://console.developers.google.com/project)
      go to the Compute > Compute Engine section.
      1. Click the "New instance" button.
      1. For the 'Boot Disk' select a Linux machine image like Debian or Ubuntu.
      1. Click the "Management, disk, networking, access & security options"
      section to expand it.
        1.  Select the "Access and Security" subsection and then select the
        "Compute" drop-down menu to set its scope.
          *  Set the "Compute" access scope to be "Read/Write".
      1. Click the "Create" button.
      1. Once the VM is created click the VM instance's "SSH" button to ssh
    in to the newly created VM instance.

1. Code checkout instructions:
  1. Prerequisites: install [Java 7 or Java 8 JDK][2], [Git][7], and [Maven][8].
You may need to set your `JAVA_HOME` environment variable as well.
    * To install these prerequisites on a Linux (Debian or Ubuntu) based Compute Engine VM
    instance, run these commands:
    <pre>
    sudo apt-get update
    sudo apt-get install git maven openjdk-7-jdk -y
    </pre>
  1. Download the sample code by running the following commands:
  <pre>mkdir some_directory
  cd some_directory
  git clone https://github.com/GoogleCloudPlatform/compute-getting-started-java.git
  cd compute-getting-started-java</pre>
   <pre># In a text editor open the ComputeEngineSample.java file. For example, to edit the file with nano:
  nano src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java</pre>

  1. In your text editor update the `YOUR_PROJECT_ID` value in
  [`src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java`][5]
so that the following line is updated. Not performing this step will result
in an error; specifically, "Parameter 'project' must conform to the pattern...".
For more information see setting your [Project ID][6].
  <pre>private static final String projectId = "YOUR_PROJECT_ID"</pre>
  1. Specify an 'Application Name' for your app by updating the following line of code:
  <pre>private static final String APPLICATION_NAME = "";</pre>
  1. Save the changes to the file and exit the text editor.

1. Compile and run the sample:
  1. Compile the sample code using Maven by running the following command:
  <pre>mvn compile</pre>
  1. Execute the sample code using Maven by running the following command:
  <pre>mvn -q exec:java</pre>
  1. Running the sample will list all Google Compute Engine VM instances found in
    the zone you specified. The sample will also check for the existence of a VM instance
    named "my-sample-instance". If the "my-sample-instance" VM does not exist, running the
    sample will create it. If the "my-sample-instance" VM does already exist then running the
    sample will delete it.

      You can verify the list of VM instances by running the command
    `gcloud compute instances list`. VM instances can be deleted with the 'gcloud compute instance delete'
    command. For example, this command will delete the 'my-sample-instance' VM instance
    in the zone 'us-central1-f':
       `gcloud compute instances delete my-sample-instance --zone us-central1-f`

1. Importing the code into Eclipse and running it from there:
  1. Prerequisites: install [Eclipse][9] and the [Maven plugin for Eclipse][10].
  1. Download code as specified above.
  1. File -> Import -> Maven -> Existing Maven Projects -> Next.
  1. Select your project directory as your "Root Directory," and click "Finish."
  1. Right-click on project compute-engine-cmdline-sample.
  1. Run As > Java Application.
  1. If asked, type or select "ComputeEngineSample" and then click OK.
  1. Application output will display in the Eclipse Console.

[1]: https://developers.google.com/compute
[2]: http://java.com/en/download/faq/develop.xml
[3]: https://developers.google.com/compute
[4]: https://console.developers.google.com/project
[5]: https://github.com/GoogleCloudPlatform/compute-getting-started-java/blob/master/src/main/java/com/google/api/services/samples/computeengine/cmdline/ComputeEngineSample.java#L51
[6]: https://developers.google.com/console/help/new/#projectnumber
[7]: http://git-scm.com/downloads
[8]: http://maven.apache.org/download.html
[9]: http://www.eclipse.org/downloads/
[10]: http://download.eclipse.org/technology/m2e/releases/
