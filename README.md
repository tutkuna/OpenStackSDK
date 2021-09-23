#  OpenStack Manila API v2 support in OpenStackSDK
## 1.   Vision and Goals Of The Project:
- Implementing features of the Manila API to the OpenStack Python SDK to be ready for the OpenStack Yoga release cycle.

## 2. Users/Personas Of The Project:
- End-users of Manila
- People that use OpenStack to develop their public cloud environment projects
- 

## 3.   Scope and Features Of The Project:
- The features of the OpenStack Shared File System API all fall within the scope of this project. Though the individual features we will be working on have not been decided yet by the mentors.
- Some possible API Features we will be working on (descriptions copied over from API documentation):

  - Managing/ Unmanaging Snapshots
    - Use the Shared File Systems service to make snapshots of shares. A share snapshot is a point-in-time, read-only copy of the data that is contained in a share. The APIs below allow controlling share snapshots. They are represented by a “snapshot” resource in the Shared File Systems service, and they can have user-defined metadata such as a name and description.
Users can create, manage, update, and delete share snapshots. Users can create a share from it, or can also revert a share to its most recent snapshot through OpenStack SDK.
  - Managing/ Unmanaging Shares
    - A share is a remote, mountable file system. In the APIs below, a share resource is a representation of this remote file system within the Shared File Systems service. This resource representation includes useful metadata, communicating the characteristics of the remote file system as determined by the user and the Shared File Systems service.
Users can create a share and associate it with a network, list shares, and show information for, update, and delete a share through OpenStack SDK.
  - Managing/ Unmanaging Shares Servers
    - A share server is created by multi-tenant back-end drivers where shares are hosted. For example, with the generic driver, shares are hosted on Compute VMs.
Administrators can perform read and delete actions for share servers. An administrator can delete an active share server only if it contains no dependent shares. If an administrator deletes the share server, the Shared File Systems service creates a share server in response to a subsequent create share request.

## 4. Solution Concept
![alt text](https://wiki.openstack.org/w/images/4/43/Shares_Service.png)
- https://wiki.openstack.org/wiki/Manila 

## 5. Acceptance criteria
- Implement a good (not-yet-determined) amount of features of the OpenStack Shared File Systems (Manila) API into the OpenStack Python SDK, create strenuous unit tests for them, and push them to the github branch https://github.com/openstack/openstacksdk/tree/feature/r1/openstack/shared_file_system/v2 .
- Minimum acceptance criteria and stretch goals not yet specified by mentors.

## 6.  Release Planning:
- We will be implementing individual API features including tests for all features we implement and releasing features into the github branch individually in a weekly/bi-weekly manner. (not fully confirmed yet by mentors, but we will losely follow the OpenStack Yoga release cycle)
- Sprint 1: Signing up for the accounts necessary to contribute to OpenStack. Keeping in touch with the mentors. Figuring out the first steps we will be taking, the features we will implement.
- Sprint 2: Starting work on implementing features we will have decided on in sprint 1.


