# wmio_project_e1
Webm.io Integration Tenants

Create a webMethods integration user across all your managed Cloud
tenants.

Username: "refplatform"

![A white screen with a black text Description automatically generated
with medium
confidence](media/image1.png)


![A screenshot of a computer Description automatically
generated](media/image2.png)


![A black and white image of a black object Description automatically
generated with medium
confidence](media/image3.png)


![A screenshot of a computer Description automatically
generated](media/image4.png)


![A screenshot of a computer Description automatically
generated](media/image5.png)


Follow the email instructions to set the password for the newly craeted
"replatform" user. This password will be used in subsequent sections.

Similarly create webMethods io integration user for other environments

![A screenshot of a computer Description automatically
generated](media/image6.png)


![A screenshot of a computer Description automatically
generated](media/image7.png)


![A screenshot of a computer Description automatically
generated](media/image8.png)


GitHub Enterprise

Create a Fork from
<https://github.webmethods.io/insrsa/webmethods_io_int_cicd> under your
account.

Generate Personal Access Token (PAT) for the Github Enterprise repo
under your GitHub Enterprise account

<https://github.webmethods.io/roti/webmethods_io_int_cicd>

[~~https://github.softwareag.com/roti/webmethods_io_int_cicd~~](https://github.softwareag.com/roti/webmethods_io_int_cicd)

**Please note that Software AG Github Enterprise URL has been changed
from github.softwareag.com to github.webmethods.io**

![](media/image9.png)


Go to Developer Settings and Generate a new PAT

![A screenshot of a computer Description automatically
generated](media/image10.png)


Select appropriate OAuth Scopes

The recommended scopes for the token: repo, user, admin:repo_hook.

![](media/image11.png)


Login to your Azure Devops Organization and create a new project

<https://dev.azure.com/roti0771/>

![](media/image12.png)


Create a Service connection to the Github Enterprise Server

![](media/image13.png)


![A screenshot of a computer Description automatically
generated](media/image14.png)


Choose PAT as Authentication Method from dropdown

Server url is the github enterprise's url

Service connection name can be a meaningful string

Verify and Save

![A screenshot of a computer screen Description automatically
generated](media/image15.png)


![A screenshot of a computer Description automatically
generated](media/image16.png)


Create the Azure Pipeline

![A screenshot of a computer Description automatically
generated](media/image17.png)


![A screenshot of a computer Description automatically
generated](media/image18.png)


![](media/image19.png)


Select the Previously Forked repository

![A screenshot of a computer Description automatically
generated](media/image20.png)


Choose existing Azure Pipeline YAML file from the forked repo

![A screenshot of a computer Description automatically
generated](media/image21.png)


Save the pipeline

![A close-up of a computer screen Description automatically
generated](media/image22.png)


![A screenshot of a computer Description automatically
generated](media/image23.png)


Rename the pipeline

![A screenshot of a computer Description automatically
generated](media/image24.png)


![A screenshot of a computer Description automatically
generated](media/image25.png)


![A white rectangular object with black text Description automatically
generated](media/image26.png)


SCM-\> Get the details of the Github repo.

The development assets of webm.io (like workflow, flowservice etc. )
will be stored in this SCM repositories.

Login to the Github account

![](media/image27.png)


Generate PAT, follow same steps as were followed for Github Enterprise
Server account. Make sure to give proper scope privileges

![](media/image28.png)


Create a New GitHub type Service Connection

![A white rectangular object with a black stripe Description
automatically generated with medium
confidence](media/image29.png)


![A screenshot of a phone Description automatically
generated](media/image30.png)


![A screenshot of a computer Description automatically
generated](media/image31.png)


![](media/image32.png)


**[Azure DevOps Server]{.underline}**

Generate the PAT for Azure Devops Account. This token will be used to
connect from Github Enterprise to Azure Devops Account.

![A screenshot of a computer Description automatically
generated](media/image33.png)


Provide the scope as Build -\> Read&Write

![](media/image34.png)


Copy the generated PAT and keep it handy.

![A screenshot of a message Description automatically
generated](media/image35.png)


Create the Variable Groups under Library

Create Group for variables used to connect to Azure Devops Organization

![A screenshot of a computer Description automatically
generated](media/image36.png)


Give the value of token as PAT that was earlier generated under Azure
Devops Organization

![](media/image37.png)


Assign pipeline permission, to be used in "initialize" pipeline

![](media/image38.png)


![A screenshot of a computer Description automatically
generated](media/image39.png)


![A screenshot of a computer Description automatically
generated](media/image40.png)


Create another Group for variables used to connect to Github server
using PAT(generated earlier) and Git hub's owner userid

![A screenshot of a computer Description automatically
generated](media/image41.png)


Assing pipeline permission

![A screenshot of a web page Description automatically
generated](media/image42.png)


Create another Group for variables used to connect to Webm.io Tenants
and invoke administrative APIs.

![A screenshot of a computer Description automatically
generated](media/image43.png)


Assign pipeline permissions

![A screenshot of a computer Description automatically
generated](media/image44.png)


Update the Tenant details under Github Enterprise Repository for play
and dev environments.

![A screenshot of a computer Description automatically
generated](media/image45.png)


![](media/image46.png)


Update the repo user details. This user will be used to connect to
Github and administer Repos.

![A screenshot of a computer Description automatically
generated](media/image47.png)


Define the Variables explicitly before running the pipeline

![A screenshot of a computer Description automatically
generated](media/image48.png)


![A screenshot of a computer Description automatically
generated](media/image49.png)


![](media/image50.png)


Run the Pipeline

![](media/image51.png)


![A screenshot of a computer Description automatically
generated](media/image52.png)


![A screenshot of a computer Description automatically
generated](media/image53.png)


![A screenshot of a computer Description automatically
generated](media/image54.png)


Import sample Assets(webmethods_io_int_cicd/assets/workflows/) into Play
environment

![](media/image55.png)


![A screenshot of a computer Description automatically
generated](media/image56.png)


![A screenshot of a computer Description automatically
generated](media/image57.png)


Import synchronizeToFeature pipeline from Github enterprise

![A screenshot of a computer Description automatically
generated](media/image58.png)


Declare variables

![A screenshot of a computer Description automatically
generated](media/image59.png)


Add pipeline permissions to the existing Library Groups

![A screenshot of a computer Description automatically
generated](media/image60.png)


![A screenshot of a computer Description automatically
generated](media/image61.png)


Get the "TriggerBuild" Task from the Market Place

![A screenshot of a computer Description automatically
generated](media/image62.png)


![A screenshot of a computer Description automatically
generated](media/image63.png)


![](media/image64.png)


![A screenshot of a computer Description automatically
generated](media/image65.png)


![A screenshot of a computer Description automatically
generated](media/image66.png)


![A screenshot of a computer Description automatically
generated](media/image67.png)


Run the pipeline

![A screenshot of a phone Description automatically
generated](media/image68.png)


![](media/image69.png)


![A screenshot of a phone Description automatically
generated](media/image70.png)


Changes reflected in featureA branch of Github repo

![A screenshot of a computer Description automatically
generated](media/image71.png)


Create a Pull Request to merge the feature branch to dev branch

![A screenshot of a computer Description automatically
generated](media/image72.png)


![A screenshot of a computer Description automatically
generated](media/image73.png)


![A screenshot of a computer Description automatically
generated](media/image74.png)


![A screenshot of a computer Description automatically
generated](media/image75.png)


![A screenshot of a computer Description automatically
generated](media/image76.png)


Add a new existing Pipeline

![A screenshot of a computer Description automatically
generated](media/image77.png)


Save

Rename Pipeline

![A screenshot of a computer Description automatically
generated](media/image78.png)


Assign pipeline permissions to the Group Variables

![A screenshot of a computer Description automatically
generated](media/image79.png)


![A screenshot of a web page Description automatically
generated](media/image80.png)


Make sure that dev.yml file is up to date with the DEV Target web.io
Tenant details

![A screenshot of a computer Description automatically
generated](media/image81.png)
Update the
/assets/github/workflows/dev.yml to point to the Azure Devops
Organization project's URL

![A screenshot of a computer Description automatically
generated](media/image82.png)


Define Variables for the Pipeline

![](media/image83.png)


Run the Pipeline with below inputs for Variables

![](media/image84.png)


![A screenshot of a phone Description automatically
generated](media/image85.png)


![A screenshot of a computer Description automatically
generated](media/image86.png)


![A screenshot of a computer Description automatically
generated](media/image87.png)


Project imported in Target DEV tenant

![](media/image88.png)


Add a new Existing Pipeline, to be used for "Testing"

![A screenshot of a computer Description automatically
generated](media/image89.png)


Declare Variables and Save the pipeline

![A screenshot of a search bar Description automatically
generated](media/image90.png)


Add(Commit and Push) Test scripts/test data to the FeatureBranch of the
concerned Project

\*\*currently a bug, so need to update Webhook id in the test data

Update

![A screenshot of a computer Description automatically
generated](media/image91.png)


Run the pipeline with below Variables as Input

![A screenshot of a computer Description automatically
generated](media/image92.png)


Give the required permission to the Pipeline

![A black rectangular object with text Description automatically
generated with medium
confidence](media/image93.png)


![A screenshot of a computer Description automatically
generated](media/image94.png)


![A screenshot of a phone Description automatically
generated](media/image95.png)


![A screenshot of a phone Description automatically
generated](media/image96.png)


Update the Permissions of the Test pipeline to allow other Pipelines to
Queue Build

Manage security

![A screenshot of a computer Description automatically
generated](media/image97.png)


![A screenshot of a computer Description automatically
generated](media/image98.png)

