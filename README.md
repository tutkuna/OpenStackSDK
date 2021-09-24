#  OpenStack Manila API v2 support in OpenStackSDK
Manila is an open source OpenStack Shared File System service that is a software that exists within the OpenStack cloud. It is a collection of microservices and other components that provide self-service management of elastic file system storage infrastructure that can allow you to work with and provision storage via 30+ storage technologies over file system protocols. It is unique in how it is able to add RESTful semantics to consuming shared storage in a reliable and scalable manner

![manila](https://wiki.openstack.org/w/images/4/43/Shares_Service.png)

credits: https://wiki.openstack.org/wiki/Manila
## 1.   Vision and Goals Of The Project:
Extending functionality of the python OpenStack Software Development Kit (OpenStackSDK) to cover more REST APIs exposed by the OpenStack Shared File Systems service (Manila)

## 2. Users/Personas Of The Project:
Users of the OpenStack Manila API can be mainly divided into two categories:  
### a. administrators  
  Their goal is to tune and offer Manila to the end users. For e.g. there are APIs that deal with the management of services such as health of micro-service, setting up templates, limiting the user access, limiting the data bandwidth or usage, failure recovery, setting rules for consumption & et al. Users with administrator role will be dealing with such tasks while utilizing Manila
### b. users  
  These are the users that utilize the Manila service with perfect setup from administrator. We can define some of the tasks performed by them as: creating a shared file system, snapshotting file system, controlling access to file system, backup and recovery of file system, etc.

Following are the most common personas based on the tasks done by OpenStack end users:
- ### Adrian - infrastructure architect
  Adrian is responsible for the strategy and road-map for his company’s cloud and identifies reasons to compel management to adopt OpenStack for production environments.
- ### Rey - cloud operator
  Rey is involved in installing, operating, using, and updating the OpenStack cloud services.
- ### Taylor - domain operator
  Taylor manages the relationship with the cloud services provider. This includes managing quotas, number of users, applicable policies, and support tickets.
- ### Wei - project owner
  Wei manages projects by adding or removing project members’ access to the cloud instance. Wei’s main concern is to have enough resources available to support Wei’s projects.
- ### Quinn - application developer
  Quinn develops and deploys cloud applications but does not necessarily know much about the underlying infrastructure of the cloud.
<!-- - End-users of Manila
- People that use OpenStack to develop their public cloud environment projects
- Some major companies using openStack: Adobe, American Express, Best buy, Bloomberg
- Few services that can be achieved using manila are:
  - **Database as a service**: With a database as a service model, application owners do not have to install and maintain the database themselves. Instead, the database service provider takes responsibility for installing and maintaining the database, and application owners are charged according to their usage of the service. It is similar to software as a service.
  - **Big Data**: Through Manila’s HDFS native driver plugin, users can create a highly scalable, flexible, fast, and cost effective storage platform, because it can store and distribute very large data sets across hundreds of inexpensive servers that operate in parallel.
  - **cross-tenant data sharing**: a tenant is a group of users sharing common access to a software instance with specific privileges. As manila is a shared file system, we can use its capabilities to achieve data-sharing between multiple tenants. This can help software to run in a distributed environment ensuring that all the different instances are sharing the same data. -->

## 3.   Scope and Features Of The Project:
The features of the OpenStack Shared File System API all fall within the scope of this project. Though the individual features we will be working on have not been decided yet by the mentors. Some possible API Features we will be working on (descriptions copied over from API documentation):  
- Managing/ Unmanaging Snapshots
  - Use the Shared File Systems service to make snapshots of shares. A share snapshot is a point-in-time, read-only copy of the data that is contained in a share. The APIs below allow controlling share snapshots. They are represented by a “snapshot” resource in the Shared File Systems service, and they can have user-defined metadata such as a name and description. Users can create, manage, update, and delete share snapshots. Users can create a share from it, or can also revert a share to its most recent snapshot through OpenStack SDK.
- Managing/ Unmanaging Shares
  - A share is a remote, mountable file system. In the APIs below, a share resource is a representation of this remote file system within the Shared File Systems service. This resource representation includes useful metadata, communicating the characteristics of the remote file system as determined by the user and the Shared File Systems service.
Users can create a share and associate it with a network, list shares, and show information for, update, and delete a share through OpenStack SDK.
- Managing/ Unmanaging Shares Servers
  - A share server is created by multi-tenant back-end drivers where shares are hosted. For example, with the generic driver, shares are hosted on Compute VMs.
Administrators can perform read and delete actions for share servers. An administrator can delete an active share server only if it contains no dependent shares. If an administrator deletes the share server, the Shared File Systems service creates a share server in response to a subsequent create share request.

## 4. Solution Concept
![process image](https://github.com/tutkuna/cs6620/blob/main/Screenshot%202021-09-23%20194854.jpg)

- Our end solution is an SDK for Python that contains helper methods to call the Manila API, which offers on-demand, scalable, robust, self-service access to shared file system storage resources. 
- We will be using Python to develop the SDK, GitHub for version control, and Gerrit for maintaining the workflow.


## 5. Acceptance criteria
- Implement a good (not-yet-determined) amount of features of the OpenStack Shared File Systems (Manila) API into the OpenStack Python SDK, create strenuous unit tests for them, and push them to the github branch https://github.com/openstack/openstacksdk/tree/feature/r1/openstack/shared_file_system/v2 .
- Minimum acceptance criteria and stretch goals not yet specified by mentors.

## 6.  Release Planning:
- We will be implementing individual API features including tests for all features we implement and releasing features into the github branch individually in a weekly/bi-weekly manner. (not fully confirmed yet by mentors, but we will losely follow the OpenStack Yoga release cycle)
- Sprint 1: Signing up for the accounts necessary to contribute to OpenStack. Keeping in touch with the mentors. Figuring out the first steps we will be taking, the features we will implement.
- Sprint 2: Starting work on implementing features we will have decided on in sprint 1.


