# appengine
Sample app engine project using GCP 

oogle Cloud Shell is a virtual machine that is loaded with development tools. It offers a persistent 5GB home directory and runs on the Google Cloud. Google Cloud Shell provides command-line access to your GCP resources.

In GCP console, on the top right toolbar, click the Open Cloud Shell button.

Cloud Shell icon

Click Continue. cloudshell_continue.png

It takes a few moments to provision and connect to the environment. When you are connected, you are already authenticated, and the project is set to your PROJECT_ID. For example:

Cloud Shell Terminal

gcloud is the command-line tool for Google Cloud Platform. It comes pre-installed on Cloud Shell and supports tab-completion.

You can list the active account name with this command:

gcloud auth list
Output:

Credentialed accounts:
 - <myaccount>@<mydomain>.com (active)
Example output:

Credentialed accounts:
 - google1623327_student@qwiklabs.net
You can list the project ID with this command:

gcloud config list project
Output:

[core]
project = <project_ID>
Example output:

[core]
project = qwiklabs-gcp-44776a13dea667a6
Full documentation of gcloud is available on Google Cloud gcloud Overview .
Task 1: Initialize App Engine
Initialize your App Engine app with your project and choose its region:

gcloud app create --project=$DEVSHELL_PROJECT_ID
When prompted, select the region where you want your App Engine application located.

Clone the source code repository for a sample application in the hello_world directory:

git clone https://github.com/GoogleCloudPlatform/python-docs-samples
Navigate to the source directory:

cd python-docs-samples/appengine/standard_python3/hello_world
Task 2: Run Hello World application locally
In this task, you run the Hello World application in a local, virtual environment in Cloud Shell.

Ensure that you are at the Cloud Shell command prompt.

Execute the following command to download and update the packages list.

sudo apt-get update
Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system.

sudo apt-get install virtualenv
If prompted [Y/n], press Y and then Enter.
virtualenv -p python3 venv
Activate the virtual environment.

source venv/bin/activate
Navigate to your project directory and install dependencies.

pip install  -r requirements.txt
Run the application:

python main.py
Please ignore the warning if any.
In Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application.
To access the Web preview icon, you may need to collapse the Navigation menu.

Result:

hello_world.png

To end the test, return to Cloud Shell and press Ctrl+C to abort the deployed service.

Using the Cloud Console, verify that the app is not deployed. In the Cloud Console, on the Navigation menu (Navigation menu), click App Engine > Dashboard.

Notice that no resources are deployed.

Task 3: Deploy and run Hello World on App Engine
To deploy your application to the App Engine Standard environment:

Navigate to the source directory:

cd ~/python-docs-samples/appengine/standard_python3/hello_world
Deploy your Hello World application.

gcloud app deploy
If prompted "Do you want to continue (Y/n)?", press Y and then Enter.
This app deploy command uses the app.yaml file to identify project configuration.

Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com

