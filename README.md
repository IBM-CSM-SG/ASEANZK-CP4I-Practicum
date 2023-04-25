# APAC PRACTICUM WORKSHOP

## IBM Cloud Pak for Integration (CP4I)

**Refer to below table for Cloud Pak For Integration (CP4I) Practicum Lab Exercise Book.**

|  Scenario                                | Use Case Description                                                        | CP4D Products Used |    Authors        
|------------------------------------------|-----------------------------------------------------------------------------|--------------------|-------------------
| [Scenario1](/scenario1/README.md)        | ABC are a Medium sized bank that offers Investments to its high value customers. The bank receive FX (Foreign Exchange) data from a 3rd party via a feed. The data from this 3rd party feed is removed once it reaches an age of two weeks. <BR><BR> As part of a new program at the bank they want to offer access to FX data up to 12 months old via a mobile app to their brokers. The raw data is not in the format required for the business users. <BR><BR> The Bank historically use IIB and MQ and have bought CP4I. They have also setup a test system to investigate the use of OpenShift and CloudPaks. |  Event Streaming (IBM Event Stream) <BR><BR> Application Integration (IBM App Connect Enterprise)| <strong>Sujatha</strong> Sureshkumar <BR><BR>Pham Manh <strong>Hung</strong>  |
|||||
| [Scenario2](/scenario2/README.md)        | The XYZ Bank still has a core banking system running on IBM System Z. Currently the only way to integrate with this system is via MQ. The core banking system provides typical account functions such as query balance, deposit and withdraw. <BR><BR>The Bank has initiated a digital transformation program to modernize their channel applications such as Internet Banking, using reactive technology to make it more user friendly and compelling to their customers. They want to user APIs in order to quickly unlock their assets in the legacy systems - so that their channel applications can consume. <BR><BR>Security is paramount, they need to ensure that the APIs exposed needs to be secured using client id/secret and OAuth/OIDC. Architect and build a solution that enable the customer to expose their digital assets via APIs using Cloud Pak for Integration. Each transaction should trigger events that can be audited or based on business rules trigger alerts.| API Management (IBM API Connect)<BR><BR>Application Integration (IBM App Connect Enterprise)<BR><BR>Enterprise Messaging (IBM MQ) | <strong>Sandeep</strong> Ved<BR><BR><strong>Glen</strong> Christian   |
|||||
| [Scenario3](/scenario3/README.md)      |  Your customer has been a long-time user of App Connect (IIB/WMB) and MQ. They have recently decided to investigate the value of modernizing their integration. They are eager to explore IBM Agile Integration practices. <BR><BR>They would like you to use one of their existing flows and queue definitions to explore how to move to containerized integration. While eager to understand the modernization journey, they also have reservations on their ability to scale and manage the workload. <BR><BR>Demonstrate how to analyze, componentize, and containerize existing integration artefacts, and illustrate how to scale and monitor the new deployments.  | Enterprise Messaging (IBM MQ)<BR><BR>Application Integration (IBM App Connect Enterprise)  | <strong>Santhoshi </strong> Gopalkrishnan <BR><BR><strong>Mano </strong> Saelao 
|||||
| [Scenario4](/scenario4/README.md)      |  Your customer has been an OpenAPI definition for an exiting REST service. They have recently decided to investigate the value of modernizing their integration. They are eager to explore IBM API connect to deploy their rest services. <BR><BR>They would like you to create an API by importing the  OpenAPI definition for an existing REST service. Also configure Security endpoints, and proxy to invoke endpoint. After testing the REST API in the online developer toolkit, publish it API for their developers. <BR><BR>Demonstrate how to analyze, componentize, and containerize existing integration artefacts, and illustrate how to scale and monitor the new deployments.  | API Connect <BR><BR>Application Integration (IBM App Connect Enterprise)  | <strong>Sandeep </strong> Ved <BR><BR> Pham Manh <strong>Hung </strong>
|||||