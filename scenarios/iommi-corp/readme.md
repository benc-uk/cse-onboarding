# Iommi Corp - Modernized Customer Experience

Iommi Corp is a global company and leading provider of McGuffin services and the trading of widgets & doohickeys. Iommi is looking to modernize how their customers can access the range of services that Iommi provides, also manage their accounts etc.

Iommi Corp has reached out to Microsoft and wants to engage with CSE on a greenfield implementation of this new system in Azure. Iommi Corp is new to the cloud, so are looking for a lot of guidance, and are open to suggestions on architecture & design of the system. 

## High Level Requirements

The core of what Iommi Corp require is as follows:

- **A set of APIs** to be able to manage user profiles and other entites in the system. This is the core of what the customer wants to build. customer is interested in how they provide both public and private APIs. The specific API mechanism and routes/operations has not been agreed.
- **Backend datastore**. As this is a greenfield project, the customer is interested in exploring a range of options, NoSQL, relational, document-db, key-value etc.
- **Asynchronous interface(s)** to backend legacy system/mainframe. The backend is slow and has no direct APIs to call it. But updates to user profiles will need to be sent down to these legacy systems. The customer is thinking of some sort of message queue, but is unsure of the options they have.
- **Automated deployment** of software components & artifacts when *main* is updated (Continuous delivery) with associated testing.
- **Automated environment management** using infrastructure as code practices.

**Note**. This has been kept purposefully very ambiguous and open ended, it's rare for a customer to really come with such un-opinionated scope, however for the purposes of learning it

## Whiteboard

Below is an very high level design given to you by one of the team at Iommi Corp. It shows the basic building blocks they want in their system and the interactions. 

The red question marks '❓' on the diagram are critical areas for discussion and are technical/architecture decision points

![](whiteboard.png)

### Technical Decision Points

Below is a list of questions that should naturally arise, and should be answered and agreed on. Each is anchored on a particular domain or aspect of the system:

1. How to expose the API publicly? What form is the API going to take? What scheme will you use (REST, GraphQL, gRPC etc)? 
2. How will you host & run the APIs you are building? What about serverless? What compute & hosting options in Azure will you consider?
3. What are the APIs going to be written in? what frameworks and tooling will you use? 
4. What will the backend datastore be? What about the use of ORM? Which of the many Azure data & DB services will you select?
5. What will you use for the legacy interface? What queuing and messaging services in Azure could you use?
6. How will the cloud resources be deployed & managed? How can we repeatably deploy environments for developers and other use cases?
7. How do we run CI and tests in an automated fashion? What are our build artifacts? What do we build and when?
8.  How will automated releases happen? What triggers the release? What is the target environment or platform?

## Out Of Scope

The follow aspects can be ignored or worked around:

- Frontend, web client and UI, this is being developed by a different team. Agree and invent the shape of the API to be called
- The legacy system can mocked and assumed to exist, the key thing is to design and code a way to send data over to it, in an asynchronous fashion.
- Authentication and authorization is out of scope. Clearly this is not indicative of a real CSE engagement, however it will allow the team to focus on other concerns, and stops the exercise becoming one sidetracked by auth & identity.
