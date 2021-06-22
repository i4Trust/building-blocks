# i4Trust Building Blocks

This document describes the components of i4Trust that can be picked up, integrated together, and eventually
combined with other components in order to build the soft infrastructure and services required for creating data spaces
where smart applications from multiple domains can participate and exchange data. Smart applications participating in
such data spaces share data using the open standard APIs and rely
on common data models. Data Publication components enable the publication and discovery of
data resources in a standard manner. Relying on Marketplace services, on the other hand, participants of created 
Data Spaces can publish
offerings around access to data resources or data processing services under concrete terms and conditions which
establish data usage/access policies to be enforced and may include pricing. Finally, components implementing
Identity and Access Management (IAM) functions enable to secure that data is accessed by the right parties and that
defined access policies are enforced.


## Contents

-   [Background](#background)
-   [Technology Building Blocks](#technology-building-blocks)
    -   [Data Interoperability](#data-interoperability)
    -   [Data Sovereignty and Trust](#data-sovereignty-and-trust)
    -   [Data Value Creation](#data-value-creation)
-   [Integrating Building Blocks for data spaces](#integrating-building-blocks-for-data-spaces)
	-   [Data Service Provider](#data-service-provider)
    -   [i4Trust Marketplace](#i4trust-marketplace)




# Background

A **data space** is defined as a decentralised infrastructure for trustworthy data sharing and exchange in data
ecosystems based on commonly agreed principles. From a technical perspective, a number of **technology building blocks**
are required ensuring:

-   **Data interoperability** - Data spaces should provide a solid framework for an efficient exchange of data among
    participants, supporting full decoupling of data providers and consumers. This requires the adoption of a “common
    lingua” every participant uses, materialized in the adoption of common APIs for the data exchange, and the
    definition of common data models. Common mechanisms for traceability of data exchange transactions and data
    provenance, are also required.

-   **Data Sovereignty and trust** - Data spaces should bring technical means for guaranteeing that participants in a
    data space can trust each other and exercise sovereignty over data they share. This requires the adoption of common
    standards for managing the identity of participants, the verification of their truthfulness and the enforcement of
    policies agreed upon data access and usage control.

-   **Data value creation** - Data spaces should provide support for the creation of multi-sided markets where
    participants can generate value out of sharing data (i.e., creating data value chains). This requires the adoption
    of common mechanisms enabling the definition of terms and conditions (including pricing) linked to data offerings,
    the publication and discovery of such offerings and the management of all the necessary steps supporting the
    lifecycle of contracts that are established when a given participant acquires the rights to access and use data.

Besides the adoption of a common technology foundation, data spaces also require **governance**, that is the adoption of
a number of business, operational and organizational agreements among participants. Business agreements, for example,
specify what kind of terms and conditions can regulate the sharing of data between participants and the legal framework
supporting contracts established through the data space. Operational agreements, on the other hand, regulate policies
that have to be enforced during data space operation like, for example, compliance with GDPR (General Data Protection
Regulation) or the 2nd Payment Services Directive (PSD2) in the finance sector. They may also comprise the definition of
tools that operators of cloud infrastructures or global services supporting data spaces must implement, enabling
auditing of certain processes or the adoption of cyber-security practices. In addition, organizational agreements
establish the governance bodies (very much like ICANN for the Internet). They deal with the identification of concrete
specifications that products implementing technology building blocks in a data space should comply with, as well as the
business and operational agreements to be adopted. The complete taxonomy of building blocks required for creating data
spaces is illustrated in the following figure.

![BuildingBlocks](https://i4trust.github.io/building-blocks/img/building-blocks.png "Data Spaces Building Blocks")

Sharing of data within a given data space should not be limited to a single domain. This would severely limit the
creation of new innovative services since individuals and organizations usually act in multiple domains at the same time
and many opportunities will flourish when data generated within organizations operating in certain domain (management of
traffic in cities, for example) is shared for its exploitation in processes relevant to other domains (continuing with
the example, logistics). Therefore, technology building blocks for data spaces must be domain-agnostic. On the other
hand, they should rely on open standards, allowing multiple infrastructure and global service providers to emerge and
support data spaces, without getting locked in any particular provider. Given this, while making things work in living
labs and pilots is relatively easy, the main challenge towards definition of successful data spaces is the decision of
what concrete standards and design principles are adopted, since they have to be accepted by all participants.



## Technology Building blocks

This section describes the different components i4Trust brings materializing the different technical building blocks
enabling the soft infrastructure and global services required for creation of data spaces.

### Data Interoperability

#### Data Exchange API

tbd



#### Data Models & Formats

tbd


#### Provenance & Traceability

tbd





### Data Sovereignty and Trust

Data spaces must provide means for guaranteeing organizations joining data spaces that they can trust the other
participants and that they will be able to exercise sovereignty on their data. That requires the definition of common
building blocks, based on mature security standards that will be used by all participants in the data space.


#### Identity Management

tbd


#### Trusted exchange

tbd


#### Access & Usage Control / Policies

tbd




### Data Value Creation

Loose coupling of participants is a fundamental principle in data spaces. Data providers and consumers do not
necessarily know about each other. Therefore, it becomes essential to incorporate building blocks enabling the
management of data resources as true assets with a business value. Assets which can be published, discovered and,
eventually, traded. This way boosting the creation of multi-side markets where innovative services can be created.


#### Metadata & Discovery Services

This building block incorporates publishing and discovery mechanisms for data resources and services, making use of
common descriptions of resources, services, and participants.


#### Publication & Marketplace Services

To support the offering of data resources and services under defined terms and conditions, marketplaces must be
established. This building block supports publication of these offerings, management of processes linked to the creation
and monitoring of smart contracts (which clearly describe the rights and obligations for data and service usage), and
access to data and services.


#### Data Usage Accounting

This building block provides the basis for accounting access to and/or usage of data by different users. This in turn is
supportive of important functions for clearing, payment, and billing (including data-sharing transactions without
involvement of data marketplaces).




## Integrating Building Blocks for data spaces

This section demonstrates common setups of the integration of the different building blocks for the creation of data
spaces and links to deployment instructions for Kubernetes. It will be enriched over time.


### Data Service Provider

An NGSI based service provider can be any (right-time) data service or data processing provider. For instance, the
underlying Context Broker could provide right-time data from different external devices via the NGSI API, or receive
data for further data processing. Access to the Context Broker instance would be protected by an API PEP Proxy.

These [instructions](https://github.com/i4Trust/tutorials/tree/main/Data-Service-Provider) describe how to set up
an environment of such a data service provider based on the following components:

-   Orion Context Broker as NGSI API service provider
-   API Umbrella as API PEP Proxy (and probably PDP)
-   Keyrock as Identity Provider and Authorization Registry
-   Activation Service to allow external parties to create policies in the Authorization Registry
-   Portal demo application as an example for a simple portal application allowing external users to login using 
	their Identity Provider and sending requests to the Orion Context Broker protected by API Umbrella

In addition, all these components require different databases to be set up.


### i4Trust Marketplace

The i4Trust Marketplace is based on the FIWARE Business API Ecosystem (BAE) which allows service providers to publish offerings
around data assets, and service consumers to acquire access to them. A full instance is based on the BAE itself, the
Keyrock Identity Manager and several databases. These
[instructions](https://github.com/i4Trust/tutorials/tree/main/i4Trust-Marketplace) describe how to deploy a
full setup on Kubernetes.
