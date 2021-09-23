#  OpenStack Manila API v2 support in OpenStackSDK
## Project Description Template

The purpose of this Project Description is to present the ideas proposed and decisions made during the preliminary envisioning and inception phase of the project. The goal is to analyze an initial concept proposal at a strategic level of detail and attain/compose an agreement between the project team members and the project customer (mentors and instructors) on the desired solution and overall project direction.

This template proposal contains a number of sections, which you can edit/modify/add/delete/organize as you like.  Some key sections we’d like to have in the proposal are:

- Vision: An executive summary of the vision, goals, users, and general scope of the intended project.

- Solution Concept: the approach the project team will take to meet the business needs. This section also provides an overview of the architectural and technical designs made for implementing the project.

- Scope: the boundary of the solution defined by itemizing the intended features and functions in detail, determining what is out of scope, a release strategy and possibly the criteria by which the solution will be accepted by users and operations.

Project Proposal can be used during the follow-up analysis and design meetings to give context to efforts of more detailed technical specifications and plans. It provides a clear direction for the project team; outlines project goals, priorities, and constraints; and sets expectations.

** **

## 1.   Vision and Goals Of The Project:
- Implementing features of the Manila API to the OpenStack Python SDK to be ready for the OpenStack Yoga release cycle.

The vision section describes the final desired state of the project once the project is complete. It also specifies the key goals of the project. This section provides a context for decision-making. A shared vision among all team members can help ensuring that the solution meets the intended goals. A solid vision clarifies perspective and facilitates decision-making.

The vision statement should be specific enough that you can look at a proposed solution and say either "yes, this meets the vision and goals", or "no, it does not".

## 2. Users/Personas Of The Project:
- End-users of Manila
- People that use OpenStack to develop their public cloud environment projects
- 

This section describes the principal user roles of the project together with the key characteristics of these roles. This information will inform the design and the user scenarios. A complete set of roles helps in ensuring that high-level requirements can be identified in the product backlog.

Again, the description should be specific enough that you can determine whether user A, performing action B, is a member of the set of users the project is designed for.

** **

## 3.   Scope and Features Of The Project:
- The features of the OpenStack Shared File System API all fall within the scope of this project. Though the individual features we will be working on have not been decided yet by the mentors.
- Some possible API Features we will be working on:

Managing/ Unmanaging Snapshots

- Use the Shared File Systems service to make snapshots of shares. A share snapshot is a point-in-time, read-only copy of the data that is contained in a share. The APIs below allow controlling share snapshots. They are represented by a “snapshot” resource in the Shared File Systems service, and they can have user-defined metadata such as a name and description.
Users can create, manage, update, and delete share snapshots. Users can create a share from it, or can also revert a share to its most recent snapshot through OpenStack SDK.

- Managing/ Unmanaging Shares
A share is a remote, mountable file system. In the APIs below, a share resource is a representation of this remote file system within the Shared File Systems service. This resource representation includes useful metadata, communicating the characteristics of the remote file system as determined by the user and the Shared File Systems service.
Users can create a share and associate it with a network, list shares, and show information for, update, and delete a share through OpenStack SDK.
- Managing/ Unmanaging Shares Servers
A share server is created by multi-tenant back-end drivers where shares are hosted. For example, with the generic driver, shares are hosted on Compute VMs.
Administrators can perform read and delete actions for share servers. An administrator can delete an active share server only if it contains no dependent shares. If an administrator deletes the share server, the Shared File Systems service creates a share server in response to a subsequent create share request.


The Scope places a boundary around the solution by detailing the range of features and functions of the project. This section helps to clarify the solution scope and can explicitly state what will not be delivered as well.

It should be specific enough that you can determine that e.g. feature A is in-scope, while feature B is out-of-scope.

** **

## 4. Solution Concept
![alt text](https://wiki.openstack.org/w/images/4/43/Shares_Service.png)
- https://wiki.openstack.org/wiki/Manila 

This section provides a high-level outline of the solution.

Global Architectural Structure Of the Project:

This section provides a high-level architecture or a conceptual diagram showing the scope of the solution. If wireframes or visuals have already been done, this section could also be used to show how the intended solution will look. This section also provides a walkthrough explanation of the architectural structure.

 

Design Implications and Discussion:

This section discusses the implications and reasons of the design decisions made during the global architecture design.

## 5. Acceptance criteria
- Implement a good amount of features of the OpenStack Shared File Systems API into the OpenStack Python SDK, create strenuous unit tests for them, and push them to the github branch https://github.com/openstack/openstacksdk/tree/feature/r1/openstack/shared_file_system/v2 .
- Minimum acceptance criteria and stretch goals not yet specified by mentors.

## 6.  Release Planning:
- We will be implementing individual API features including tests for all features we implement and releasing features into the github branch individually in a weekly/bi-weekly manner. (not fully confirmet by mentors, but we will losely follow the OpenStack Yoga release cycle)
- Sprint 1: Signing up for the accounts necessary to contribute to OpenStack. Keeping in touch with the mentors. Figuring out the first steps we will be taking, the features we will implement.
- Sprint 2: Starting work on implementing features we will have decided on in sprint 1.


Release planning section describes how the project will deliver incremental sets of features and functions in a series of releases to completion. Identification of user stories associated with iterations that will ease/guide sprint planning sessions is encouraged. Higher level details for the first iteration is expected.

** **

## General comments

Remember that you can always add features at the end of the semester, but you can't go back in time and gain back time you spent on features that you couldn't complete.

** **

