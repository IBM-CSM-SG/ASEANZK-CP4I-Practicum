# APAC PRACTICUM WORKSHOP

## IBM Cloud Pak for Integration (CP4I)

**Refer to below table for Cloud Pak For Integration (CP4I) Practicum Lab Exercise Book.**

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 19%" />
<col style="width: 21%" />
<col style="width: 24%" />
<col style="width: 23%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Scenario</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Use Case Description</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>CP4D Products Used</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Authors</strong></p>
</blockquote></th>

</tr>
</thead>
<tbody>

<tr class="odd">
<td><p><u>

[Scenario1](/scenario1/README.md)
</u></p>
</td>
<td>
<p> ABC are a Medium sized bank that offers Investments to its high value customers. The bank receive FX (Foreign Exchange) data from a 3rd party via a feed.
The data from this 3rd party feed is removed once it reaches an age of two weeks.
As part of a new program at the bank they want to offer access to FX data up to 12 months old via a mobile app to their brokers. The raw data is not in the format required for the business users.
The Bank historically use IIB and MQ and have bought CP4I. They have also setup a test system to investigate the use of OpenShift and CloudPaks. </p>
</td>
<td>
<p>API Management (IBM API Connect)</p>
<p>Application Integration (IBM App Connect Enterprise)</p>
<p>Event Streaming (IBM Event Stream) </p>
</td>
<td>
<p><strong>Sujatha</strong> Sureshkumar </p>
<p>Pham Manh <strong>Hung</strong> </p>
</td>
</tr>

<tr class="even">
<td>
<p><u>

[Scenario2](/scenario2/README.md)
</u></p>
</td>
<td>
<p>The XYZ Bank still has a core banking system running on IBM System Z. Currently the only way to integrate with this system is via MQ.

The core banking system provides typical account functions such as query balance, deposit and withdraw.

The Bank has initiated a digital transformation program to modernize their channel applications such as Internet Banking, using reactive technology to make it more user friendly and compelling to their customers.

They want to user APIs in order to quickly unlock their assets in the legacy systems - so that their channel applications can consume.

Security is paramount, they need to ensure that the APIs exposed needs to be secured using client id/secret and OAuth/OIDC.

Architect and build a solution that enable the customer to expose their digital assets via APIs using Cloud Pak for Integration.

Each transaction should trigger events that can be audited or based on business rules trigger alerts.

</p>
</td>
<td>
<p>API Management (IBM API Connect)</p>
<p>Application Integration (IBM App Connect Enterprise)</p>
<p>Enterprise Messaging (IBM MQ) </p>
</td>
<td>
<p><strong>Sandeep</strong> Ved</p>
<p><strong>Glen</strong> Christian </p>
</td>
</tr>

<tr class="odd">
<td><p><u>

[Scenario3](/scenario3/README.md)
</u></p>
</td>
<td>
<p>Your customer has been a long-time user of App Connect (IIB/WMB) and MQ. They have recently decided to investigate the value of modernizing their integration. They are eager to explore IBM Agile Integration practices. They would like you to use one of their existing flows and queue definitions to explore how to move to containerized integration.
While eager to understand the modernization journey, they also have reservations on their ability to scale and manage the workload. Demonstrate how to analyze, componentize, and containerize existing integration artefacts, and illustrate how to scale and monitor the new deployments.
</p>
</td>
<td>
<p>Messaging (IBM MQ)</p>
<p>API Management (IBM API Connect)</p>
<p>Application Integration (IBM App Connect Enterprise)</p>
<p>Event Streaming (IBM Event Stream) </p>
</td>
<td>
<p><strong>Santhoshi </strong> Gopalkrishnan </p>
<p><strong>Mano </strong> Saelao </p>
</td>
</tr>

</tbody>
</table>
