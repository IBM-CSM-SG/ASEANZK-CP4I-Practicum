# IBM Cloud Pak for Integration - Configuration

[**6.1. High Level Architecture**](#_Toc105518919)

[**6.2. Prepare Client Tools**](#_Toc105518920)

- [**6.2.1 IBM App Connect Enterprise (ACE) Toolkit Setup**](#_Toc105518921)
- [**6.2.2 Openshift Command Line Interface (CLI) Setup**](#_Toc105518922)
- [**6.2.3 Mailtrap SMTP Setup**](#_Toc105518923)

[**6.3. Messaging Queue (MQ)**](#_Toc105518924)

- [**6.3.1 Create Queue Manager**](#_Toc105518925)
- [**6.3.2 Create Queue**](#_Toc105518926)
- [**6.3.3 Configure Default Channel Security**](#_Toc105518927)

[**6.4. Integration Dashboard**](#_Toc105518928)

[**6.5. Integration - ACE to MQ**](#_Toc105518929)
- [**6.5.1 Prepare - Asset into IBM ACE Toolkit**](#_Toc105518930)
- [**6.5.2 Build - BAR File**](#_Toc105518931)
- [**6.5.3 Deploy - Create a local integration server**](#_Toc105518932)

[**6.6. API Connect (APIC)**](#_Toc105518933)

- [**6.6.1 Cloud Manager (API Management Administration)**](#_Toc105518934)
  - [Create Organization](#create-organization)
  - [Configure SMTP for notifications](#configure-smtp-for-notifications)
  - [Configure admin email id](#configure-admin-email-id)
- [**6.6.2 API Manager (API Management)**](#_Toc105518938)
  - [Develop API](#develop-api)
  - [Configure API](#configure-api)
  - [Develop Product](#develop-product)
  - [Create Catalog](#create-catalog)
  - [Publish Product](#publish-product)
  - [API Connect Developer Portal](#api-connect-developer-portal)

### ------------------------------------------------------------------ ###

<span id="_Toc105518919" class="anchor"></span>**High Level
Architecture**

Below is the high level architecture that we plan to implement as part
of this scenario.

<img src="./media/image1.png" style="width:3.375in;height:3.01389in"
alt="Diagram Description automatically generated" />

<span id="_Toc105518920" class="anchor"></span>**Prepare Client Tools**

<span id="_Toc105518921" class="anchor"></span>**IBM App Connect
Enterprise (ACE) Toolkit Setup**

Install IBM App Connect Enterprise for developers (also called ACE).
Make sure to select the correct download package for your OS (Windows,
Linux, Mac).

Click on **Download** button on the following
link: [<u>https://www.ibm.com/docs/en/app-connect/12.0?topic=enterprise-download-ace-developer-edition-get-started</u>](https://www.ibm.com/docs/en/app-connect/12.0?topic=enterprise-download-ace-developer-edition-get-started)

<img src="./media/image2.png" style="width:6.26806in;height:2.87361in"
alt="Graphical user interface, text, application, Teams Description automatically generated" />

The version used in this practicum is 12.0.4

<img src="./media/image3.png"
style="width:6.26806in;height:0.70139in" />

<img src="./media/image4.png" style="width:6.26806in;height:3.37014in"
alt="Table Description automatically generated" />

Complete the installation through the installer package you just
downloaded for your OS. eg: 12.0.4.0-ACE-MAC64-DEVELOPER-UNSIGNED. You
can use the IBM ACE Installation page as a guide to complete the
installation.

Once installed, open the installed ACE toolkit. A view similar to the
screenshot below will launch.

<img src="./media/image-xx-1.png" style="width:6.26806in;height:3.37014in"
alt="Table Description automatically generated" />

<span id="_Toc105518922" class="anchor"></span>**Openshift Command Line Interface (CLI) Setup**

Download Openshift Command line tools (OC Client)

<img src="./media/image5.png" style="width:6.26806in;height:1.14375in"
alt="Background pattern Description automatically generated" />

Download OC Client for your platform

<img src="./media/image6.png" style="width:6.26806in;height:2.10486in"
alt="Graphical user interface, text, application Description automatically generated" />

Place downloaded oc binary file (oc or oc.exe )to the path in variable for your platform. See the below URL for more details.

https://docs.openshift.com/container-platform/4.8/cli_reference/openshift_cli/getting-started-cli.html 

<span id="_Toc105518923" class="anchor"></span>**Mailtrap SMTP Setup**

Signup for a SMTP account on mailtrap.io. Once logged in, note down your
SMTP connection settings. For Example,

Host: smtp.mailtrap.io

Port: 2525

User: 2ef08bdc18285b

Password: 11xxxxxx06b8da

<img src="./media/image7.png" style="width:5.31523in;height:3.09751in"
alt="Graphical user interface, text, application, email Description automatically generated" />

You can also check all your emails under MyInbox in mailtrap web site.

<img src="./media/image8.png" style="width:6.26806in;height:2.12222in"
alt="Graphical user interface, text, application Description automatically generated" />

<span id="_Toc105518924" class="anchor"></span>**Messaging Queue (MQ)**

<span id="_Toc105518925" class="anchor"></span>**Create Queue Manager**

Go to IBM Cloud Pak home. Check the IBM Cloud PAK URL from Openshift
Routes.

<img src="./media/image9.png" style="width:6.26806in;height:4.07639in"
alt="A screenshot of a computer Description automatically generated" />

Login to IBM Cloud Pak using the IBM provided credentials (admin only).

<img src="./media/image10.png" style="width:6.26806in;height:4.07639in"
alt="A screenshot of a computer Description automatically generated with medium confidence" />

Use IBM provided Authentication (admin only) and logged in with admin /
32 char password that we gave while installing CP4I.

<img src="./media/image11.png" style="width:6.26806in;height:4.07639in"
alt="A screenshot of a computer Description automatically generated" />

Go to IBM Cloud Pak Home, click on **Messaging** as highlighted in the
screen below:

<img src="./media/image12.png" style="width:6.26806in;height:3.42431in"
alt="Graphical user interface, website Description automatically generated" />

This will redirect to a Messaging screen as below. Click on Create an
instance to create a queue manager.

<img src="./media/image13.png" style="width:6.26806in;height:3.16181in"
alt="Graphical user interface, application Description automatically generated" />

Select **Quick start** option from this screen, and click on Next.

<img src="./media/image14.png" style="width:6.26806in;height:3.16181in"
alt="Graphical user interface, text, application Description automatically generated" />

Modify the details for your queue manager as below:

-   **License acceptance** – Toggle the button from OFF to ON state 

<img src="./media/image15.png" style="width:6.26806in;height:3.15903in"
alt="Graphical user interface, text, application Description automatically generated" />

-   Select **Type of availability** from dropdown as SingleInstance

<img src="./media/image16.png" style="width:6.26806in;height:3.35347in"
alt="Graphical user interface, text, application, email Description automatically generated" />

-   Select **Type of Volume** from the drop down as persistent-claim 

<img src="./media/image17.png" style="width:6.26806in;height:3.35347in"
alt="Graphical user interface, text, application Description automatically generated" />

Lastly click on **Create** from the top right corner and queue manager
will be created. You will be redirected to a new page, showing the
details of your newly created Queue manager.

<img src="./media/image18.png" style="width:6.26806in;height:3.34444in"
alt="Graphical user interface, application Description automatically generated" />

Click on queue name --\> It should open up MQ Console

<img src="./media/image19.png" style="width:6.26806in;height:3.34444in"
alt="Graphical user interface, website Description automatically generated" />

Click on manage --\> quickstart to open queue manager

<img src="./media/image20.png" style="width:6.26806in;height:3.34444in"
alt="Graphical user interface, application Description automatically generated" />

<span id="_Toc105518926" class="anchor"></span>**Create Queue**

Click on Create icon to create the queue.

<img src="./media/image21.png" style="width:6.26806in;height:3.52569in"
alt="A screenshot of a computer Description automatically generated" />

Select a Local Queue.

<img src="./media/image22.png" style="width:6.26806in;height:3.52569in"
alt="Graphical user interface, application Description automatically generated" />

Provide the details of the queue and click **create**.

<img src="./media/image23.png" style="width:6.26806in;height:3.52569in"
alt="Graphical user interface, application, Word Description automatically generated" />

Queue will be created shortly.

<img src="./media/image24.png" style="width:6.26806in;height:3.52569in"
alt="A screenshot of a computer Description automatically generated" />

<span id="_Toc105518927" class="anchor"></span>**Configure Default
Channel Security**

Copy Login Commands to login to oc client.

<img src="./media/image25.png" style="width:6.26806in;height:1.12847in"
alt="Background pattern Description automatically generated" />

Login to Openshift cluster using oc client.

<img src="./media/image26.png" style="width:6.26806in;height:2.48264in"
alt="Graphical user interface, text, application, Teams Description automatically generated" />

oc
login --token=sha256\~WT3FGc2jTkW0gM539MizrLUT-D7sm8RMmP4tTgKRF-g --server=https://c111-e.us-east.containers.cloud.ibm.com:30273

run below command to see all your projects.

oc projects

Run below command to switch to your project.

oc project \<projectname\>

Run below command to see the pod name of the mq queue manager.

oc get pods \| grep -i mq

Run the sample given script to configure the mq security. Make sure that
you have execution permission on the samples scripts loadmq.sh and
mq_ace_lab.mqsc.

./loadmq.sh mq-quickstart-cp4i-ibm-mq-0

This script performs:

-   Disable Chlauth security

-   Disable clientauth security

-   Disable user security on MQ objects level

<span id="_Toc105518928" class="anchor"></span>**Integration Dashboard**

Navigate to Administration -\> Integration Instances.

<img src="./media/image27.png" style="width:6.26806in;height:4.07639in"
alt="A screenshot of a computer Description automatically generated" />

Click on the hamburger on top left --\> click Integration Instances

<img src="./media/image28.png" style="width:6.26806in;height:1.48333in"
alt="Text Description automatically generated" />

Click “Create Instance” on top right of the page

<img src="./media/image29.png" style="width:6.26806in;height:1.80625in"
alt="Graphical user interface, application Description automatically generated" />

Select Integration Dashboard and click next

<img src="./media/image30.png" style="width:6.26806in;height:1.54167in"
alt="Graphical user interface, application Description automatically generated" />

Select either Production or Quick Start --\> click next

<img src="./media/image31.png" style="width:6.26806in;height:2.42361in"
alt="Graphical user interface, application Description automatically generated" />

Key-in the details of the environment and proceed to create the
dashboard.

<img src="./media/image32.png" style="width:6.26806in;height:4.71111in"
alt="Graphical user interface, text, application, email Description automatically generated" />

Upon successful creation of Integration Dashboard below message will
appear on the browser.

<img src="./media/image33.png" style="width:6.26806in;height:1.31319in"
alt="Graphical user interface Description automatically generated with medium confidence" />

<span id="_Toc105518929" class="anchor"></span>**Integration - ACE to
MQ**

Integration has the following components:

-   [<u>Prepare</u>](#_Toc105518930)

-   [<u>Build</u>](#_Toc105518931)

-   [<u>Deploy</u>](#_Toc105518932)

<span id="_Toc105518930" class="anchor"></span>**Prepare - Asset into
IBM ACE Toolkit**

Open IBM ACE Toolkit under a workspace and create a REST API project.

<img src="./media/image34.png" style="width:4.93056in;height:3.79167in"
alt="Graphical user interface, text, application, chat or text message Description automatically generated" />

Give it a name and select the specification as Swagger 2.0 Click Finish.

<img src="./media/image35.png" style="width:6.26806in;height:3.23611in"
alt="Graphical user interface, text, application Description automatically generated" />

Open the REST API Description. Under Resources, Click on + icon to
create a resource.

<img src="./media/image36.png" style="width:6.26806in;height:3.23611in"
alt="Graphical user interface, text Description automatically generated" />

Enter the resource path and select the operation as post. Click Apply.

<img src="./media/image37.png" style="width:6.26806in;height:3.28125in"
alt="Graphical user interface, application Description automatically generated" />

A New resource will be created.

<img src="./media/image38.png" style="width:6.26806in;height:2.93264in"
alt="Graphical user interface, application Description automatically generated" />

Click on the subflow icon or this new resource.

<img src="./media/image39.png" style="width:6.26806in;height:2.97986in"
alt="Graphical user interface, application, Teams Description automatically generated" />

New subflow editor will open. Drag the IBM MQ Connector from the
transformation section in the left toolbox.

<img src="./media/image40.png" style="width:6.26806in;height:2.94306in"
alt="Graphical user interface, application Description automatically generated" />

Connect the Boxes together.

<img src="./media/image41.png" style="width:6.26806in;height:2.21597in"
alt="Graphical user interface Description automatically generated" />

Find the MQ Queue Manager Service IP address from the “openshift
console” or oc client (oc get svc \| grep -i mq).

<img src="./media/image42.png" style="width:6.19444in;height:0.80556in"
alt="Text Description automatically generated with medium confidence" />

<img src="./media/image43.png" style="width:6.26806in;height:3.50833in"
alt="Graphical user interface, application Description automatically generated" />

Note the default System Server Connection Channel name
(SYSTEM.DEF.SVRCONN).

<img src="./media/image44.png" style="width:6.26806in;height:3.47847in"
alt="Graphical user interface, application Description automatically generated" />

Click on the MQ Output and configure the MQ Details. Enter the Queue
Name.

<img src="./media/image45.png" style="width:6.26806in;height:2.93333in"
alt="Graphical user interface, text, application Description automatically generated" />

Enter the MQ Connection Details like Queue Manager Name, Queue Manager
Host Name (Service IP), Listener Port no (1414 Default), Connection
Channel Name (default – SYSTEM.DEF.SVRCONN).

<img src="./media/image46.png" style="width:6.26806in;height:4.87153in"
alt="Graphical user interface, application Description automatically generated" />

<span id="_Toc105518931" class="anchor"></span>**Build – BAR File**

Add a new BAR file in the project to package and export the
configuration.

<img src="./media/image47.png" style="width:4.14412in;height:4.90741in"
alt="Graphical user interface, application Description automatically generated" />

Enter the bar file details and click Finish.

<img src="./media/image48.png" style="width:4.40476in;height:3.77426in"
alt="Graphical user interface, text, application, email Description automatically generated" />

Include the newly created project. Add the Build options and Click Save.

<img src="./media/image49.png" style="width:6.26806in;height:2.37639in"
alt="Graphical user interface, text, application Description automatically generated" />

Rebuild BAR and save file one more time.

<img src="./media/image50.png" style="width:6.26806in;height:2.02083in"
alt="Graphical user interface, text, application, email Description automatically generated" />

<img src="./media/image51.png" style="width:4.02778in;height:1.30556in"
alt="Graphical user interface, text, application, email Description automatically generated" />

<img src="./media/image52.png" style="width:3.875in;height:1.41667in"
alt="Graphical user interface, text, application, chat or text message Description automatically generated" />

Check the properties of the generated bar file.

<img src="./media/image53.png" style="width:2.61111in;height:4.86111in"
alt="Graphical user interface, text, application Description automatically generated" />

Copy the bar file path or open it in finder window.

<img src="./media/image54.png" style="width:5.90278in;height:3.95833in"
alt="Graphical user interface, text, application, email Description automatically generated" />

<span id="_Toc105518932" class="anchor"></span>**Deploy - Create a local
integration server**

Proceed further to create a Local Integration Server in ACE. You may do
so by using the navigation -

Right click on the Integration Servers --\> Select **Create a local
Integration Server**

<img src="./media/image55.png" style="width:6.26806in;height:3.67361in"
alt="Graphical user interface, application Description automatically generated" />

Click Create a Server and Chose a Quick Start Plan. Click Next.

<img src="./media/image56.png" style="width:6.26806in;height:2.80347in"
alt="Graphical user interface, text, application, Teams Description automatically generated" />

Drag and Drop the newly generated bar file here. Click Next.

<img src="./media/image57.png" style="width:6.26806in;height:2.47778in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click Next.

<img src="./media/image58.png" style="width:6.26806in;height:2.39167in"
alt="Graphical user interface, text, application, Teams Description automatically generated" />

Enter the Integration Server Name, Select License. Click Create.

<img src="./media/image59.png" style="width:6.26806in;height:3.40556in"
alt="Graphical user interface, text, application Description automatically generated" />

The Integration Server will be created and ready shortly. You may
refresh the page to check on the readiness status update.

<img src="./media/image60.png" style="width:5.42857in;height:2.43762in"
alt="Graphical user interface, text, application Description automatically generated" />

Click on the Server once its ready.

<img src="./media/image61.png" style="width:2.62963in;height:2.90407in"
alt="Graphical user interface, application Description automatically generated" />

Click on the API.

<img src="./media/image62.png" style="width:3.05952in;height:2.55006in"
alt="Graphical user interface, application Description automatically generated" />

Click on the <u>post/AccountEnquiry.</u>

<img src="./media/image63.png" style="width:6.27545in;height:3.20238in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click on Try It Tab to test the Rest Interface.

<img src="./media/image64.png" style="width:6.29107in;height:3.41667in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click on Generate to generate a random test message. Click Send.

<img src="./media/image65.png" style="width:6.077in;height:3.40476in"
alt="Graphical user interface, application, Teams Description automatically generated" />

The response should come successfully.

<img src="./media/image66.png" style="width:6.26806in;height:2.95in"
alt="Graphical user interface, application, Teams Description automatically generated" />

This completes the creation and testing of local integration server.

<span id="_Toc105518933" class="anchor"></span>**API Connect (APIC)**

Navigate to Administration -\> Integration Instances.

<img src="./media/image67.png" style="width:6.26806in;height:1.44514in"
alt="Rectangle Description automatically generated with low confidence" />

Create an instance of the API Connect (API Management) .

<img src="./media/image68.png" style="width:6.26806in;height:4.07639in"
alt="Graphical user interface, application Description automatically generated" />

Chose the basic one node plan. Click Next.

<img src="./media/image69.png" style="width:6.26806in;height:4.07639in"
alt="Graphical user interface, application, Word Description automatically generated" />

Enter the API instance Name and accept the license. Enter the license
ID.

<img src="./media/image70.png" style="width:6.26806in;height:4.07639in"
alt="Graphical user interface, application Description automatically generated" />

Optionally select the matching Storage Class. Click Finish.

<img src="./media/image71.png"
style="width:6.26806in;height:4.07639in" />

API Connect Instances will be created.

-   **API Managed Enterprise Gateway** is the data power gateway.

-   **API Management** is the instance where we can configure/Develop
    new APIs Products and catalog. (API Manager).

-   **API Management Administration** is where we can create
    organization, configure authentication settings, SMTP settings etc .

<img src="./media/image72.png" style="width:6.26806in;height:2.44097in"
alt="Graphical user interface, application Description automatically generated" />

<span id="_Toc105518934" class="anchor"></span>**Cloud Manager (API
Management Administration)**

#### Create Organization

Click on the API Management Administration Link to open Cloud Manager
Console.

Click Manage Organization.

<img src="./media/image73.png" style="width:6.26806in;height:3.9in"
alt="Graphical user interface, application, website Description automatically generated" />

Click on Add to create an API organization which is like a logical
separation of multiple API users.

<img src="./media/image74.png" style="width:6.26806in;height:2.09931in"
alt="Graphical user interface, text, application, Teams Description automatically generated" />

Enter the Organization Name.

<img src="./media/image75.png" style="width:6.26806in;height:3.81736in"
alt="Graphical user interface, application Description automatically generated" />

Change the User Registry to Common Services User Registry. Enter the
existing user name as admin. Click Create.

<img src="./media/image76.png" style="width:6.26806in;height:3.47361in"
alt="Graphical user interface, application Description automatically generated" />

<img src="./media/image77.png" style="width:6.26806in;height:0.99074in"
alt="Graphical user interface, application, Teams Description automatically generated" />

#### Configure SMTP for notifications

Click on Resource’s link in the left pane.

<img src="./media/image78.png" style="width:6.26806in;height:3.80417in"
alt="Graphical user interface, application Description automatically generated" />

Click on Notification Link.

<img src="./media/image79.png" style="width:6.26806in;height:1.80208in"
alt="Graphical user interface Description automatically generated with medium confidence" />

Add a new smtp server for email notifications. You can add any smtp
provider eg. Sendgrid or mailtrap or any other.

<img src="./media/image80.png" style="width:6.26806in;height:3.82569in"
alt="Graphical user interface, application, email Description automatically generated" />

Click test email to test the connection. Enter the recipient email id
and click Send Test Email.

<img src="./media/image81.png" style="width:4.38889in;height:1.48611in"
alt="Graphical user interface, application, Teams Description automatically generated" />

The email should be sent successfully.

<img src="./media/image82.png" style="width:4.36111in;height:1.45833in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click Save to save the config.

<img src="./media/image83.png" style="width:6.26806in;height:1.42778in"
alt="A picture containing graphical user interface Description automatically generated" />

Also update the same email smtp settings for the Dummy mail server as
well.

<img src="./media/image84.png" style="width:6.26806in;height:1.34653in"
alt="Graphical user interface, application Description automatically generated" />

#### Configure admin email id

In the Cloud Manager, Under Manage Organization, Go to Logged in User
(admin) Settings and click My Account.

<img src="./media/image85.png" style="width:6.26806in;height:1.66736in"
alt="Graphical user interface Description automatically generated" />

Update the email id for the current account. Very Important. Otherwise
later you will not be able to create a portal service under a catalog.

<img src="./media/image86.png" style="width:6.26806in;height:2.83889in"
alt="Graphical user interface, application Description automatically generated" />

<span id="_Toc105518938" class="anchor"></span>**API Manager (API
Management)**

Click on the API Management Link to open API Management Console. If you
see below picture then your Organization is not set correctly.

<img src="./media/image87.png" style="width:6.26806in;height:3.89306in"
alt="Graphical user interface, application, website Description automatically generated" />

After setting the organization correctly, the API Manager should look
like this.

<img src="./media/image88.png" style="width:6.26806in;height:3.95278in"
alt="Graphical user interface, application, website Description automatically generated" />

#### Develop API

Click on Develop APIs and products. Create a new API. This will
encapsulate the API created on the ACE.

<img src="./media/image89.png" style="width:6.26806in;height:1.47917in"
alt="Graphical user interface, application Description automatically generated" />

Lets chose the basic one (default) with no validation. Click Next.

<img src="./media/image90.png" style="width:6.26806in;height:3.97292in"
alt="Graphical user interface Description automatically generated with medium confidence" />

Provide the details for Target service.

<img src="./media/image91.png" style="width:6.26806in;height:4.67431in"
alt="Graphical user interface, application Description automatically generated" />

Note the Target Service URL from Integration Dashboard that we created
earlier.

<img src="./media/image92.png" style="width:6.26806in;height:2.28194in"
alt="Graphical user interface, application, Teams Description automatically generated" />

<http://is-01-toolkit-http-cp4i-practicum-scenario2.cp4intpg-wdc04-mdh7qi-8946bbc006b7c6eb0829d088919818bb-0000.us-east.containers.appdomain.cloud/myequiry/v1/AccountEnquiry>

Enter the title of the API. This will also create an endpoint / base
path using which the API can be called and it will just redirect the
request to Target Service URL.

<img src="./media/image93.png" style="width:6.26806in;height:4.67431in"
alt="Graphical user interface, application Description automatically generated" />

Click Next.

<img src="./media/image94.png" style="width:6.26806in;height:1.76042in"
alt="Graphical user interface Description automatically generated with low confidence" />

Click Edit API.

<img src="./media/image95.png" style="width:6.26806in;height:1.76319in"
alt="A picture containing background pattern Description automatically generated" />

#### Configure API

After Clicking Edit API, API Design Screen will open.

<img src="./media/image96.png" style="width:6.26806in;height:4.67431in"
alt="Graphical user interface, application Description automatically generated" />

As we are exposing only post service in the backend we can delete the
other operations from here.

<img src="./media/image97.png" style="width:6.26806in;height:3.94167in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click Save.

<img src="./media/image98.png" style="width:5.53435in;height:4.12715in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Under Security Schema Click Add to add another security schema.

<img src="./media/image99.png" style="width:6.26806in;height:4.67431in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Select apiKey as the security definition key.

<img src="./media/image100.png" style="width:6.26806in;height:3.12083in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Enter the details as below.

<img src="./media/image101.png" style="width:6.26806in;height:4.79028in"
alt="Graphical user interface, application Description automatically generated" />

Client Secret is added as security schema. Click Save.

<img src="./media/image102.png" style="width:6.14652in;height:4.58367in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Go to General -\> Security . Edit the security schema name.

<img src="./media/image103.png" style="width:6.17732in;height:4.60664in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Select both parameter and Click Submit.

<img src="./media/image104.png" style="width:6.26806in;height:2.27083in"
alt="Graphical user interface, text, application Description automatically generated" />

Click Save.

<img src="./media/image105.png" style="width:6.26806in;height:2.58958in"
alt="Graphical user interface, application Description automatically generated" />

Now make this API online so that it will be published in a development
sandbox.

<img src="./media/image106.png" style="width:2.73611in;height:0.625in"
alt="Graphical user interface Description automatically generated" />

<img src="./media/image107.png" style="width:2.73611in;height:0.625in"
alt="Graphical user interface, text, application Description automatically generated" />

#### Develop Product

Go to Home again and develop API and Products.

<img src="./media/image108.png" style="width:6.26806in;height:3.35208in"
alt="Graphical user interface, application, website Description automatically generated" />

Now we need to package this API into a product. One product can have
multiple APIs.

<img src="./media/image109.png" style="width:6.26806in;height:1.54722in"
alt="Graphical user interface, application Description automatically generated" />

Click Add -\> Product.

<img src="./media/image110.png" style="width:6.26806in;height:1.54722in"
alt="Graphical user interface Description automatically generated with medium confidence" />

Click Next.

<img src="./media/image111.png" style="width:6.26806in;height:1.96389in"
alt="A picture containing background pattern Description automatically generated" />

Give a product Name. Click Next.

<img src="./media/image112.png" style="width:6.26806in;height:2.67778in"
alt="Graphical user interface, application Description automatically generated" />

Select an API to be added into this product. Click Next.

<img src="./media/image113.png" style="width:6.26806in;height:2.17222in"
alt="Graphical user interface, application Description automatically generated" />

Review the plan details. You can more plans by clicking on Add Button.
Can define the new plan name and rate limit (eg. API Calls Frequency).

<img src="./media/image114.png" style="width:6.26806in;height:3.65in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click Next After adding the required plans.

<img src="./media/image115.png" style="width:6.26806in;height:4.46736in"
alt="Graphical user interface, application Description automatically generated" />

Click Next with default options.

<img src="./media/image116.png" style="width:6.26806in;height:3.44861in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Click Done. We will publish it separately later after creating catalog.

<img src="./media/image117.png" style="width:6.26806in;height:2.05764in"
alt="Graphical user interface, application Description automatically generated" />

New product is added with the new API.

<img src="./media/image118.png" style="width:6.26806in;height:1.68611in"
alt="Graphical user interface, application Description automatically generated" />

Go to API Manager Manage Settings to update the email Notification
settings.

<img src="./media/image119.png" style="width:6.26806in;height:3.42431in"
alt="Graphical user interface, application Description automatically generated" />

Go to Notifications.

<img src="./media/image120.png" style="width:6.26806in;height:1.81042in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Configure the sender name and email address.

<img src="./media/image121.png" style="width:6.26806in;height:1.81042in"
alt="Graphical user interface, application Description automatically generated" />

<img src="./media/image122.png" style="width:6.26806in;height:1.81042in"
alt="Graphical user interface, application Description automatically generated" />

#### Create Catalog

Now we can create a catalog. One catalog can contain one developer
portal where this product can be published. We can have a internal and
external catalog where internal catalog is for internal organization and
external is for external users.

Go to manage catalogs under API Manager.

<img src="./media/image123.png" style="width:6.26806in;height:3.69583in"
alt="Graphical user interface, application, website Description automatically generated" />

Create new Catalog.

<img src="./media/image124.png" style="width:6.26806in;height:1.95278in"
alt="Graphical user interface, application, website Description automatically generated" />

Enter a name and Click Create

<img src="./media/image125.png" style="width:6.26806in;height:2.72431in"
alt="Graphical user interface, application Description automatically generated" />

Open the new Catalog and navigate to Catalog settings.

<img src="./media/image126.png" style="width:6.26806in;height:1.94306in"
alt="Graphical user interface, text, application Description automatically generated" />

<img src="./media/image127.png" style="width:6.26806in;height:2.99097in"
alt="Graphical user interface, text, application, email Description automatically generated" />

Create a developer portal here.

<img src="./media/image128.png" style="width:6.26806in;height:2.99097in"
alt="Graphical user interface, application, website Description automatically generated" />

Click Create. If the email if is not updated for the logged in user
account, then there will be an error mentioning so. Update the admin
user email id from Cloud Manager -\> My Account as explained earlier.
Also make sure smtp settings are correct under Cloud Manager
notification settings.

<img src="./media/image129.png" style="width:6.26806in;height:2.39097in"
alt="Graphical user interface, text, application, email Description automatically generated" />

It will take a few minutes for the portal service to be ready. You will
receive an email once its ready to set the password for the portal admin
account.

<img src="./media/image130.png" style="width:6.26806in;height:2.53403in"
alt="Graphical user interface, text, application Description automatically generated" />

#### Publish Product

Now lets publish the product to the new catalog from API Manager first.
So it can be visible in this catalog.

<img src="./media/image131.png" style="width:6.26806in;height:2.43472in"
alt="Graphical user interface, application Description automatically generated" />

Select the new catalog. You can set the catalog visibility to
Authenticated users. Click Publish. It will be published shortly.

<img src="./media/image132.png" style="width:6.26806in;height:3.93889in"
alt="Graphical user interface, application, Teams Description automatically generated" />

#### API Connect Developer Portal

(optional) Once you receive the email to set the password click on that
link and set the password for the admin account for API Manager.

Note down the Portal API URL from **Catalog Settings -\> Portal** and
open it in Mozilla Browser. Eg.

<https://apis-minim-27578f6b-portal-web-cp4i-practicum-scenario2.cp4intpg-wdc04-mdh7qi-8946bbc006b7c6eb0829d088919818bb-0000.us-east.containers.appdomain.cloud/api-org-3/practicum-catalog>

**Note:** Use **Mozilla Browser** only for this as there will be issues
with chrome browser with default self-signed certificate settings and
chrome will prevent the connection.

<img src="./media/image133.png" style="width:6.26806in;height:3.85972in"
alt="Graphical user interface, application Description automatically generated" />

Click on **Create Account** to create a new account.

<img src="./media/image134.png" style="width:6.26806in;height:2.82292in"
alt="Graphical user interface, application Description automatically generated" />

You will receive email with activation instructions.

<img src="./media/image135.png" style="width:5.45833in;height:4.51389in"
alt="Graphical user interface, text, application, email Description automatically generated" />

The account will be activated and you will be able to login with the
newid. Sign in with the new id and password.

<img src="./media/image136.png" style="width:6.26806in;height:3.85972in"
alt="Graphical user interface, application, Word Description automatically generated" />

Click on Create a new App.

<img src="./media/image137.png" style="width:5.56071in;height:4.78014in"
alt="Graphical user interface, application Description automatically generated" />

Enter an application Name and click Save.

<img src="./media/image138.png" style="width:5.76829in;height:3.47337in"
alt="Graphical user interface, application Description automatically generated" />

Once application created successfully, note down the Key and Secret for
this application. You can not see the Key and Secret for this
application after this page. Each application will interact with API
Manager/ACE using this client secret. Click OK.

<img src="./media/image139.png" style="width:6.26806in;height:2.83333in"
alt="Graphical user interface, application Description automatically generated" />

-   Key: 81b789b18XXXXXXXXXX069ec1757beb9

-   Secret: 0a38029dXXXXXXXXXXa16f47aa943eb

You can optionally click on verify link to verify your secret against
this application’s key.

Click on **Why not browse the available APIs** to subscribe to API
Product for this App.

<img src="./media/image140.png" style="width:4.74234in;height:3.52908in"
alt="Graphical user interface Description automatically generated with medium confidence" />

Click on the published API product.

<img src="./media/image141.png" style="width:5.65466in;height:2.86499in"
alt="A picture containing graphical user interface Description automatically generated" />

Just click on the **Select** button for one of the plan exposed by the
product.

<img src="./media/image142.png" style="width:6.26806in;height:4.06875in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Select the **application** to be subscribed.

<img src="./media/image143.png" style="width:6.26806in;height:2.04861in"
alt="Graphical user interface, application Description automatically generated" />

To confirm subscription, click Next.

<img src="./media/image144.png" style="width:6.26806in;height:1.08056in"
alt="Graphical user interface, application Description automatically generated" />

Click Done.

<img src="./media/image145.png" style="width:6.26806in;height:1.08056in"
alt="Graphical user interface, application Description automatically generated" />

Click on **POST /** option under overview, in the left pane.

<img src="./media/image146.png" style="width:6.26806in;height:2.08264in"
alt="Graphical user interface, application Description automatically generated" />

Click on **Try It** tab to test this API product.

<img src="./media/image147.png" style="width:6.26806in;height:2.75556in"
alt="Graphical user interface, application, Teams Description automatically generated" />

Enter the API Secret for authentication and click Send.

<img src="./media/image148.png" style="width:6.26806in;height:2.00556in"
alt="Graphical user interface, application, Teams Description automatically generated" />

If you receive an error like below, then it could be because you are
using any other browser than Firefox. Or the Certificate is not trusted.

<img src="./media/image149.png" style="width:6.26806in;height:2.60694in"
alt="Graphical user interface, text, application Description automatically generated" />

Open this URL in the error below in the browser and accept the
certificate. Ignore the error.

<img src="./media/image150.png"
style="width:6.26806in;height:0.29722in" />

Now You can try to send the API call one more time, you should be able
to see the response successfully.

<img src="./media/image151.png" style="width:6.26806in;height:2.07639in"
alt="Graphical user interface, application Description automatically generated" />

Check in the IBM MQ if this message has been stored in Queue
Successfully. Go to Integration Instances -\> Messaging instance Name
-\> Manage -\> Queue name

<img src="./media/image152.png" style="width:6.26806in;height:2.65764in"
alt="Graphical user interface, table Description automatically generated" />

[Go to Configuration Index](#ibm-cloud-pak-for-integration---configuration)

[Go back to -> Table of Contents](../README.md)

[Go to next topic -> Conclusion](../Conclusion/README.md)