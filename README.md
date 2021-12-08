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
The features of the OpenStack Shared File System API all fall within the scope of this project, but we have taken on resources as prioritized by our mentors and managed to implement 8 of them.

The API Features we have worked on:  
* Share Instance Export Location
  * Export locations are the file path where we can find a particular resource. This resource will list and give details about the export locations for the share instances
  * Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/814326
* Share Type
  * This resource creates a share type that can be used while creating a share replica. There are three types of share types: Readable, writable and Disaster recovery
  * Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/79702
- Share Replica
  - These are the replicated copies of a share which are used for syncing data and as a disaster recovery solution. The replicas depends on the type of the share and so we need to have a share type before we can create a share Replica.
 	- Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/815765
- Share Instance:
  - These are the instances of the share that are stored on different locations in the shared file system. Operations on these can only be done by the administrators
  - Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/814327 
- Share Replica Export Location 
  -  Like explained earlier, this resource allows users to list and get details about the export locations for a given share replica. Again, export locations are the file path where we can find the share replica once it is exported
  - Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/818014 
- Share Group Type 
  - A share group type enables users to filter or choose back ends before they create a share group. It can be either private or public. By default it is public.  I basically implemented the group specs functionality corresponding to the before mentioned group capabilities.
  - Functional Tests pending.
- Share Group Snapshot
  -  is a point-in-time, read-only copy of the data that is contained in a share group.
  - Patch Link:  https://review.opendev.org/c/openstack/openstacksdk/+/817891
- Revert Share to Snapshot
  - This is a function for share and share snapshot, the share snapshot is a point-in-time copy of a share, with this function user can revert a share to its most recent  snapshot.

Patch Link: https://review.opendev.org/c/openstack/openstacksdk/+/819559
## 4. Solution Concept
![process image](https://github.com/tutkuna/cs6620/blob/main/Screenshot%202021-09-23%20194854.jpg)

- Our end solution is an SDK for Python that contains helper methods to call the Manila API, which offers on-demand, scalable, robust, self-service access to shared file system storage resources. 
- We will be using Python to develop the SDK, GitHub for version control, and Gerrit for maintaining the workflow.


## 5. Acceptance criteria
- Implement a good amount of features of the OpenStack Shared File Systems (Manila) API into the OpenStack Python SDK, create strenuous unit and functional tests for them, and push them to the gerrit page https://review.opendev.org/q/project:openstack%252Fopenstacksdk as patches for review.
- Stretch goals would be getting our patches reviewed, all review feedback handled, and the patches merged to the release code.


## 6.  Release Planning:
- We will be working on implementing individual API features including tests for all features we implement and publishing our patches to the gerrit page individually in a bi-weekly manner. 
- Sprint 1: Signing up for the accounts necessary to contribute to OpenStack. Keeping in touch with the mentors. Figuring out the first steps we will be taking, the features we will implement. (~1 week)
- Sprint 2: Starting work on implementing share instances, share instance export locations, and share group snapshots. (2 weeks)
- Sprint 3: Finish up testing for share instances, continue working on share group snapshots. Start implementing share group types and share replicas. (2 weeks)
- Sprint 4: Start implementing share replica export locations. Continue with share group types, finish up share group snapshots. Fix share types (previous contributor’s patch) (2 weeks)
- Sprint 5: Participate in Manila Bugsquash. Address mentors’ feedback on share instances patch to get it ready for merging. Still finishing up functional tests for share group types. Adding tests for share replica. (2 weeks)


