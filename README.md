# i4Trust Building Blocks

This repository describes the components of i4Trust that can be picked up, integrated together, and eventually 
combined with other components in order to build the soft infrastructure and services required for creating data 
spaces where smart applications can participate and exchange data. Smart applications participating in i4Trust 
data spaces share digital twin data using the open standard NGSI-LD API and relying on common data models. Data 
Publication components enable the publication and discovery of data resources in a standard manner. Relying on 
Marketplace services, on the other hand, participants in i4Trust Data Spaces can publish offerings around access 
to digital twin data resources or data processing services under concrete terms and conditions which establish 
data usage/access policies to be enforced and may include pricing. Finally, components implementing Identity and 
Access Management (IAM) functions enable to ensure that data is accessed by trusted parties and that defined access 
policies are enforced.

> :information_source: **i4Trust Building Blocks Document**  
> The i4Trust Building Blocks document contains a detailed description about i4Trust Data Spaces, the 
> different Building Blocks and the reference examples.
>
> *Download: [:arrow_down:](https://i4trust.github.io/building-blocks/docs/i4Trust-BuildingBlocks_v3.0.pdf)
> (Version 3.0, 09/2022)*


In the case of questions just contact us
* by sending a mail to helpdesk(at)i4trust.org or
* by visiting the [i4Trust Helpdesk](https://spaces.fundingbox.com/spaces/i4trust-i4trust-helpdesk) and posting 
  a question (Hit the button "New" and select "Questions i4Trust Technical")



## Contents

-   [Background](#background)
-   [Technology Building Blocks](#technology-building-blocks)
    -   [Data Interoperability](#data-interoperability)
    -   [Data Sovereignty and Trust](#data-sovereignty-and-trust)
    -   [Data Value Creation](#data-value-creation)
-   [Integrating Building Blocks for the creation of i4Trust data spaces](#integrating-building-blocks-for-the-creation-of-i4trust-data-spaces)
	-   [Data Service Provider](#data-service-provider)
    -   [i4Trust Marketplace](#i4trust-marketplace)




## Background

A data space is defined as a decentralised infrastructure for effective and trustworthy data sharing in data ecosystems 
based on commonly agreed principles. From a technical perspective, a number of technology building blocks are 
required ensuring:

-   **Data interoperability** - Data spaces should provide a solid framework for an effective exchange of data among 
	participants, supporting full decoupling of data providers and consumers. This requires the adoption of 
	a “common lingua” every participant uses, materialized in the adoption of common APIs for the data exchange, and 
	the definition of common data models. Common mechanisms for traceability of data exchange transactions and data 
	provenance, are also relevant.

-   **Data Sovereignty and trust** - Data spaces should bring technical means for guaranteeing that participants in a 
	data space can trust each other and exercise sovereignty over data they share. This requires the adoption of common 
	standards for managing the identity of participants, the verification of their truthfulness and the enforcement of 
	policies defined for data access and usage control.

-   **Data value creation** - Data spaces should provide support for the creation of multi-sided markets where 
	participants can generate value out of sharing data (i.e., creating data value chains). This requires the adoption 
	of common mechanisms enabling the definition of terms and conditions (including pricing) linked to data offerings, 
	the publication and discovery of such offerings and the management of all the necessary steps, including clearing, 
	payment and billing functions, supporting the lifecycle of contracts that are established when a given participant 
	acquires the rights to access and use data.

Besides the adoption of a common technology foundation, data spaces also require governance, that is the adoption of a 
number of business, operational and organizational agreements among participants. Business agreements, for example, 
specify what kind of terms and conditions can regulate the sharing of data between participants and the legal framework 
supporting contracts established through the data space. Operational agreements, on the other hand, regulate policies 
that have to be enforced during data space operation like, for example, compliance with 
GDPR (General Data Protection Regulation) or the 2nd Payment Services Directive (PSD2) in the finance sector. They may 
also comprise the definition of tools that operators of cloud infrastructures or global services supporting data spaces 
must implement, enabling auditing of certain processes or the adoption of cyber-security practices. In addition, 
organizational agreements establish the governance bodies (very much like ICANN for the Internet). They deal with the 
identification of concrete specifications that products implementing technology building blocks in a data space should 
comply with, as well as the business and operational agreements to be adopted. The complete taxonomy of building blocks 
required for creating data spaces is illustrated in the following figure.

![BuildingBlocks](https://i4trust.github.io/building-blocks/img/building-blocks.png "Data Spaces Building Blocks")

Sharing of data within a given data space should not be limited to a single domain. This would severely limit the creation 
of new innovative services since individuals and organizations usually act in multiple domains at the same time and many 
opportunities will flourish when data generated within organizations operating in certain domain (data related to traffic 
in cities, for example) is shared for its exploitation in processes relevant to other 
domains (continuing with the example, logistics). Therefore, technology building blocks for data spaces must 
be domain-agnostic. On the other hand, they should rely on open standards, allowing multiple infrastructure and global 
service providers to emerge and support data spaces, without getting locked in any particular provider. Given this, 
while making things work in living labs and pilots is relatively easy, the main challenge towards definition of successful 
data spaces is the decision of what concrete standards and design principles are adopted, since they have to be accepted 
by all participants.



## Technology Building blocks

This section describes the different open source components i4Trust brings, materializing the different technical building 
blocks enabling the soft infrastructure and global services required for the creation of data spaces.


### Data Interoperability

#### Data Exchange API

Data providers joining data spaces must be able to publish data resources at well defined endpoints knowing that data consumers, 
unknown by them a priori, will know how to retrieve and consume data through those endpoints. Data consumers, on the other 
hand, must know how data available through endpoints they discover can be consumed. This is achieved by adopting domain-agnostic 
common APIs for data exchange.

In i4Trust data spaces, participants are expected to exchange digital twin data, that is the values of attributes characterizing 
entities representing physical world objects (e.g., a street, a room within a floor of a building, a vehicle) or real world 
concepts (e.g., a trouble ticket, an alarm).

The **NGSI API** is the API used in i4Trust for the exchange of digital twin data. Many different systems have been developed 
using it in domains such as smart cities, smart manufacturing, smart energy, smart water, smart agrifood, smart ports, or smart 
health. Digital twin data exchange based on the NGSI API is supported by any of the existing 
FIWARE [Core Context Broker components](https://github.com/FIWARE/catalogue#core-context-broker-components) (Orion-LD, Scorpio 
or Stellio).




#### Data Models & Formats

Combined with the data exchange APIs, achieving full interoperability also requires the adoption of common data models to be 
represented in formats compatible with the API. 
The [Smart Data Model](https://github.com/smart-data-models) initiative provides a library of data model specifications 
mapped into concrete JSON and JSON-LD data structures compatible with the NGSI-LD API, therefore suitable for supporting data 
interoperability in i4Trust data spaces.




#### Provenance & Traceability

FIWARE brings components which provide the means for tracing and tracking in the process of data provision and data 
consumption/use. It provides the basis for a number of important functions, from identification of the provenance of data to 
audit-proof logging of NGSI-LD transactions. For those data spaces with strong requirements on transparency and certification, 
FIWARE brings components (i.e., [Canis Major](https://github.com/FIWARE/CanisMajor)) that ease recording of transaction logs 
into different **Distributed Ledgers / Blockchains**.




### Data Sovereignty and Trust


#### Identity Management

The building block of Identity Management allows identification, authentication, and authorization of organizations, 
individuals, machines and other actors participating in a data space. 
FIWARE brings the [Keyrock](https://github.com/ging/fiware-idm) component which 
supports [OpenIdConnect](https://openid.net/connect/), 
[SAML 2.0](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html) 
and [OAuth2](https://oauth.net/2/) standards. Quite relevant for data spaces deployed in Europe, Keyrock also resolves 
integration with [eIDAS](https://ec.europa.eu/cefdigital/wiki/display/CEFDIGITAL/eID), a building block provided by the 
European Commission that enables the mutual recognition of national electronic identification schemes (eID) across borders, 
allowing European citizens and legal entities to use their national eIDs when accessing online services from other 
European countries. Additionally, regional certificates that match the requirements similar to eIDAS are legally recognized 
for the purpose of digital signatures and can be added and made interoperable.
In addition to Keyrock, FIWARE also brings [VCBackend](https://github.com/FIWARE/VCBackend) and [VCWaltid](https://github.com/FIWARE/VCWaltid) to support [SIOP-2](https://openid.net/specs/openid-connect-self-issued-v2-1_0.html) and [OIDC4VP](https://openid.net/specs/openid-connect-4-verifiable-presentations-1_0-07.html).

#### Trusted exchange

Trusted data exchange among participants provides certainty that participants involved in the data exchange are who they 
claim to be, and that they comply with defined rules/agreements. Trust refers to the fact that data providers and data 
consumers can rely on the identity of the members of the data ecosystem and beyond that, between different security domains.

[iSHARE](https://ishareworks.atlassian.net/wiki/spaces/IS/overview) brings a scheme that enables organizations to give each 
other access to their data. It results in a set of agreements 
which improve circumstances for data exchange and focuses on the topics of Identification, Authentication and 
Authorisation. From a technical perspective, iSHARE is an authentication & authorization protocol for both machine2machine (M2M) 
and human2machine (H2M) communication based on a JSON REST API architecture. Authentication is heavily based on Public Key 
Infrastructure (PKI) and therefore certificates and public / private key pairs. iSHARE relies heavily on signed JSON Web Tokens 
for protecting the integrity of message content. Every party of iSHARE validates signatures and interprets the content of JWTs. 
Every party creates and signs these tokens depending on the context. The Scheme Owner (iSHARE Satellite) is playing the role of 
a trust authority providing a trusted framework 
which keeps the scheme, and its network of participants, operating properly. Every participant to the iSHARE Scheme must have a 
relation with the Scheme Owner, and can check at the Scheme Owner whether other parties participate in iSHARE and are trustable. 



#### Access & Usage Control / Policies

Access and usage control guarantees enforcement of data access and usage policies defined as part of the terms and conditions established 
when data resources or services are published or negotiated between providers and consumers. An API proxy plays the role of the 
Policy Enforcement Point (PEP) and requires an additional Policy Decision Point (PDP). 
In the current release of i4Trust, PEP and PDP functionalitie provided via libraries in [lua](https://github.com/FIWARE/lua-fiware-lib). The libraries can be used to implement plugins for various api-gateways, with a solution for the [Kong API-Gateway](https://github.com/Kong/kong) already [implemented by FIWARE](https://github.com/FIWARE/kong-plugins-fiware).
The PDP functionality for authorization via VerifiableCredentials is provided as an additional component, the [DSBA-PDP](https://github.com/FIWARE/dsba-pdp) and can be integrated into the flow, using the same [Kong-Plugins](https://github.com/FIWARE/kong-plugins-fiware) as PEP.
The [DSBA-PDP](https://github.com/FIWARE/dsba-pdp) uses the [EBSI Trusted Issuers Registry API](https://api-pilot.ebsi.eu/docs/apis/trusted-issuers-registry/latest#/) for evaluating if an issuer is allowed to issue certain credentials. The PDP provides a compatibility mechanism to use the [iShare delegation endpoint](https://dev.ishareworks.org/delegation/endpoint.html) as trusted issuers source. Additionally, the [iShare delegation endpoint](https://dev.ishareworks.org/delegation/endpoint.html) is used to evaluate the actual policies referenced by the roles in the received credential.

In addition, [Keyrock](https://github.com/ging/fiware-idm) also implements Policy Administration Point (PAP) and Policy 
Management Point (PMP) standard [XACML](https://en.wikipedia.org/wiki/XACML) functions.

For defining access policies, iSHARE brings the 
[delegation evidence data model](https://dev.ishareworks.org/delegation/delegation-evidence.html) which is structured according 
to a JSON port of 
the XACML standard. A key functionality of iSHARE is delegating rights to another party, authorising them to act on your behalf. 
In that sense, a delegation evidence expresses the delegation of rights from a delegator to the delegate . Rights are expressed in 
rules in terms of allowed actions to be performed on resources, under the licenses as defined in policySets.

Authorization capabilities through the SIOP-2/OIDC4VP flow are provided by [VCBackend](https://github.com/FIWARE/VCBackend) and [VCWaltid](https://github.com/FIWARE/VCWaltid). The combination of both can be used as issuer of VerfiableCredentials and as a verifier, creating [JWT's](https://jwt.io/) to access the backend secured by the [Kong-PEP](https://github.com/FIWARE/kong-plugins-fiware) and the [DSBA-PDP](https://github.com/FIWARE/dsba-pdp). A minimal wallte for storing the credentials is provided by the [VCWallet](https://github.com/FIWARE/VCWallet).



### Data Value Creation


#### Metadata & Discovery Services

Not yet part of the current release of i4Trust but soon to be incorporated, this building block incorporates publishing and 
discovery mechanisms for data resources and services, making use of common descriptions of resources, services, 
and participants.


#### Publication & Marketplace Services

To support the offering of data resources and services under defined terms and conditions, marketplaces must be
established. This building block supports publication of these offerings, management of processes linked to the creation
and monitoring of smart contracts (which clearly describe the rights and obligations for data and service usage), 
implementation of clearing house functions.

The [Business API Ecosystem](https://github.com/FIWARE-TMForum/Business-API-Ecosystem) provides sellers the means for
managing, publishing, and generating revenue of their products, apps, data, and services. The Business API Ecosystem
enables the monetization of different kinds of assets (both digital and physical) across the whole service life cycle,
from offer creation through to charging, accounting and revenue settlement and sharing. It relies on a set of standard
APIs (and its reference implementations) provided by the TMForum in its TMF API ecosystem.

Not yet part of the current release of i4Trust but soon to be incorporated, [Idra](https://github.com/OPSILab/Idra) is 
a web application able to federate existing Open Data Management Systems
(ODMS) based on different technologies providing a unique access point to search and discover open datasets coming from
heterogeneous sources. It supports natively ODMS based on CKAN, DKAN, Socrata, Orion Context Broker (NGSI v2, NGSI-LD)
and many other technologies: Idra provides also a set of APIs to federate ODMS not natively supported.


#### Data Usage Accounting

This building block provides the basis for accounting access to and/or usage of data by different users. This in turn is
supportive of important functions for clearing, payment, and billing (including data-sharing transactions without
involvement of data marketplaces).








## Integrating Building Blocks for the creation of i4Trust data spaces

This section demonstrates common setups of the integration of the different building blocks for the creation of data
spaces and links to deployment instructions for Kubernetes. It will be enriched over time.


### Data Service Provider

An NGSI based service provider can be any (right-time) data service or data processing provider. For instance, the
underlying Context Broker could provide right-time data from different external devices via the NGSI API, or receive
data for further data processing. Access to the Context Broker instance would be protected by an API PEP Proxy.

These [instructions](https://github.com/i4Trust/tutorials/tree/main/PacketDelivery-ReferenceExample/Data-Service-Provider) describe how to set up
an environment of such a data service provider based on the following components:

-   Orion Context Broker as NGSI API service provider
-   Kong as API PEP Proxy (and probably PDP)
-   Keyrock as Identity Provider and Authorization Registry
- 	DSBA-PDP as PDP for VerifiableCredentials
- 	VCBackend and VCWaltid as credentials issuer and verifier
-   Activation Service to allow external parties to create policies in the Authorization Registry
-   Portal demo application as an example for a simple portal application allowing external users to login using 
	their Identity Provider and sending requests to the Orion Context Broker protected by API Umbrella

In addition, all these components require different databases to be set up.


### i4Trust Marketplace

The i4Trust Marketplace is based on the FIWARE Business API Ecosystem (BAE) which allows service providers to publish offerings
around data assets, and service consumers to acquire access to them. A full instance is based on the BAE itself, the
Keyrock Identity Manager and several databases. These
[instructions](https://github.com/i4Trust/tutorials/tree/main/PacketDelivery-ReferenceExample/i4Trust-Marketplace) describe how to deploy a
full setup on Kubernetes.
