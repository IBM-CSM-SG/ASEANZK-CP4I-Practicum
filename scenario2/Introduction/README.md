# Introduction

### [Topic 2.1: Cloud Pak for Integration](README.md#ibm-cloud-pak-for-integration)

## IBM Cloud Pak for Integration

IBM Cloud Pak for Integration brings together IBM’s market-leading middleware capabilities to support a broad range of integration styles and use cases. With powerful deployment, lifecycle management, and production services running on Red Hat OpenShift, it enables clients to leverage the latest agile integration practices, simplify the management of their integration architecture, and reduce cost. Deployment of IBM Cloud Pak for Integration requires RedHat OpenShift cluster.

A IBM Cloud Pak® for Integration installation consists of a Red Hat® OpenShift® Container Platform cluster with one or more Cloud Pak for Integration operators installed and one or more Cloud Pak for Integration instances deployed.

In general, you can have one of the following clusters:

- **Managed OpenShift** clusters, on which some operation, monitoring and billing are integrated with the cloud-platform provider. These clusters are built and managed by the cloud-provider's interface:

    - RedHat OpenShift on IBM Cloud (ROKS)
    - RedHat OpenShift on AWS (ROSA)
    - Azure RedHat OpenShift (ARO)

- **Installer Provisioned Infrastructure (IPI)** clusters which are created using the openshift-install command. These IPI clusters can typically be enhanced to accommodate infrastructure and storage nodes using the gitops scaffolding.

    - Azure
    - AWS
    - VMware

- **User Provisioned Infrastructure (UPI)** clusters, which are built manually to accommodate an unsupported environment. Although we did not prefer this path, we understand that there are valid customer situation that may warrant the UPI implementation. However, with UPI, you are responsible on building the additional structure so that the cluster is production ready.

Several customer may also request that the cluster would not have internet access (i.e **restricted network or airgapped**). Although most can be fulfilled with IPI airgapped cluster, some specific deployment may need to be UPI.

For the purpose of this workshop, we will be installing IBM Cloud Pak for Integration on IBM ROKS

[Go back to -> Table of Contents](../README.md)

[Go to next topic -> Solution Architecture](../Architecture/README.md)