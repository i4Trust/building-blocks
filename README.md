# i4Trust Building Blocks

<!-- ToC created with: https://github.com/thlorenz/doctoc -->
<!-- Update with: doctoc README.md -->

<details>
<summary><strong>Table of Contents</strong></summary>

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


</details>




## Background

i4Trust is a collaboration program targeted to accelerate the creation of data spaces based on 
the combination of FIWARE and iSHARE building blocks enabling effective and trustful data transactions 
among participants for the creation of value.

FIWARE Foundation, iSHARE Foundation and FundingBox participate in this collaboration program, 
contributing from different angles:

* FIWARE Foundation contributes open source FIWARE Business Ecosystem Components which are the basis 
  for a) the FIWARE Data Space Connector smart organisations can deploy for connecting to data spaces 
  and b) the implementation of global intermediary services that may be part of data spaces (e.g., 
  Marketplace services, Data Publication Services).
* iSHARE Foundation contributes the open source iSHARE components, based on the iSHARE trust and legal 
  framework for data space governance, plus the expertise and mentorship  guidance on how to set up 
  governance structures for data spaces.
* FundingBox contributes their experience in management of cascade funding projects and accelerator 
  programs which can be useful in the design and implementation of acceleration programs that may 
  emerge around the application of FIWARE and/or iSHARE building blocks for data spaces.

From a technical point of view, both FIWARE Foundation and iSHARE Foundation commit to drive evolution 
of FIWARE and iSHARE technical building blocks for data spaces to comply with mature open industry standards. 
In this respect, both organisations are committed to keep alignment with recommendations about standards 
to adopt, and specifications on how adopted standards can be integrated together, that have been published as 
[Data Space Business Alliance (DSBA) Technical Convergence recommendations](https://data-spaces-business-alliance.eu/wp-content/uploads/dlm_uploads/Data-Spaces-Business-Alliance-Technical-Convergence-V2.pdf), 
and will be collaborating in bringing solutions to remaining gaps. Experience in the implementation of 
these solutions will be contributed as feedback to the DSBA Technical Convergence WG. 
The [Data Spaces Business Alliance (DSBA)](https://data-spaces-business-alliance.eu/) brings together 
the [Big Data Value Association (BDVA)](https://www.bdva.eu/), 
[FIWARE Foundation](https://www.fiware.org/), 
[Gaia-X](https://gaia-x.eu/) and 
the [International Data Spaces Association (IDSA)](https://internationaldataspaces.org/) with the common 
objective of boosting the European Data Economy through the materialisation of data spaces. Relevantly, 
DSBA Technical Convergence recommendations are endorsed and considered as a basis for the work carried out by 
the [Data Space Support Center](https://dssc.eu/) project (see 
endorsement [here](https://dssc.eu/page/Endorsements)).




## Contact

You can contact us on the FIWARE Community on Discord. Concretely, you may want to run a live conversation with us in 
one of the following channels:

* [data-space-connector](https://discord.gg/UahV9Crv3Q), where to carry out real-time discussions about the 
  FIWARE Data Space Connector
* [data-space-tef-testing-experimentation-facility](https://discord.gg/urUkDgr8Mc), where to carry out real-time discussions 
  about the FIWARE Data Space Connector as a Service Testing and Experimentation Facility (DSCaaS TEF) 
* [trust-and-decentralized-iam](https://discord.gg/WtBvSVhQS6), where to carry out real-time discussions about FIWARE 
  components implementing trust, identity management and access control. These components are planned to be used in different 
  projects (e.g., DOME) but are core components of the FIWARE Data Space Connector
* [trading-marketplace](https://discord.gg/ZVtTVTsF8Y), where to carry out real-time discussions about FIWARE components 
  implementing marketplace functions. These components are planned to be used in different projects (e.g., DOME) but are core 
  components of the FIWARE Data Space Connector.
* [ishare-i4trust-collaboration](https://discord.gg/ZfkEJNmf34) (channel), where to carry out real-time discussions about usage 
  of iSHARE building blocks in combination with the FIWARE Data Space Connector for creation of data spaces. Links to iSHARE 
  Community tools (see next sections) will be include there.
* [ishare-i4trust-collaboration](https://discord.gg/FxFKtCQQzp) (forum), configured as a forum where to consolidate answers about 
  the i4Trust collaboration program and the combined usage of FIWARE and iSHARE building blocks.

Experiments funded under the initial phase of the i4Trust collaboration program formulated questions you may found solved already. 
They can be found in 
this [i4Trust Helpdesk](https://spaces.fundingbox.com/spaces/i4trust-i4trust-helpdesk) space of the old community platform we had setup. 
We will be copying relevant questions and their response to 
the [ishare-i4trust-collaboration](https://discord.gg/FxFKtCQQzp) forum.




## Introduction to Data Spaces

A data space can be defined as a data ecosystem built around commonly agreed building blocks enabling effective and trustful data 
transactions among data space participants for the creation of value.

From a technical perspective, a data space can be built based on a number of systems that need to interoperate (see figure):

* **Data Space Connectors** organisations have to deploy in order to connect to data spaces. These data space connectors 
  implement a number of integrated modules solving how:
  - authentication of users and applications can be implemented, 
  - policies for accessing data and data processing services, as well as for usage of data, can be enforced based on attributes 
	of users and applications or characterising the environment
  - acquisition of rights to use data and data services can be managed, eventually implying payment
  - transfer of data can be controlled, 
  - transactions can be logged and audited
  - software deployed by the organisation to process data can be remotely attested
* **Data Space Global Registries** including:
  - registry of participants who have adhered to the established data space governance framework,
  - registry of trusted issuers of credentials assigned as values of attributes of users and applications
* Optionally, **intermediary systems** like for example:
  - **marketplaces**, where providers of data and data services may publish specifications of their products (defined as combination 
	of data and data services) as well as offerings defined around those products, and where ordering of products 
	(leading to provision and/or activation) can be formulated by users
  - **data publication platforms** which harvest information about data and data services offered by organisations and provide 
	means for users to discover them. 
	
![MainSystems](https://i4trust.github.io/building-blocks/img/main-systems.png "Main systems in a Data Space")

Interoperability standards for data spaces need to be defined in three major pillars:

* **Data Exchange** - Data spaces should provide a solid framework for efficient data exchange among participants, 
  supporting the complete decoupling of data providers and consumers. This requires the adoption of a “common lingua” 
  every participant uses, materialised in the adoption of common APIs for the data exchange, and the definition of common 
  data models. Common mechanisms for traceability of data exchange transactions and data provenance are also required.
* **Data Sovereignty and trust** - Data spaces should bring technical means for guaranteeing that participants in a data 
  space can trust each other and exercise sovereignty over the data they share. This requires the adoption of common standards 
  for managing the identity of participants, the verification of their truthfulness, and the enforcement of policies agreed 
  upon for accessing data and data services as well as for the usage of data.
* **Data value creation** - Data spaces should support the creation of multi-sided markets where participants can generate 
  value out of sharing data (i.e., creating data value chains). This requires the adoption of common mechanisms for specifying 
  products (defined as combination of data and data services) the definition of terms and conditions (including pricing) linked 
  to products offerings, the publication and discovery of such offerings, and the management of all the necessary steps 
  supporting the lifecycle of contracts that are established when a given participant acquires the rights to access and use 
  data after completion of a product order.
  
Besides adopting a common technology foundation, data spaces also require that participants adhere to a common governance 
framework, defined based on a number of business, operational, and organisational agreements. For example, business agreements 
specify what kind of terms and conditions can regulate data sharing between participants and the legal framework supporting 
contracts established through the data space. On the other hand, operational agreements regulate policies that must be enforced 
during data space operation, such as compliance with GDPR (General Data Protection Regulation) or the 2nd Payment Services 
Directive (PSD2) in the finance sector. They may also comprise the definition of tools that operators of cloud infrastructures 
or global services supporting data spaces must implement, enabling auditing certain processes or adopting agreed cyber-security 
practices. Last but not least, organisational agreements establish the governance bodies (very much like ICANN for the Internet) 
which govern the concrete release of standard technology specifications to be adopted, as well as business and operational 
agreements to be used. The complete taxonomy of building blocks required for creating data spaces is illustrated 
in the following figure.

![BuildingBlocks](https://i4trust.github.io/building-blocks/img/building-blocks.png "Data Spaces Building Blocks")

The task of adopting a common technology infrastructure and governance framework is daunting enough when confined to a single 
data space, where a unanimous agreement among diverse stakeholders is needed. However, the complexity escalates when 
considering the broader vision of a universal technology infrastructure and governance framework that underpins multiple 
sector-agnostic data spaces, which would not only facilitate participation across various data spaces but also enable 
seamless cross-domain data transactions, mirroring the universality and interoperability that characterise the World Wide 
Web. Achieving alignment on this scale is a formidable challenge, as it requires harmonising the interests and technical 
capabilities of many stakeholders across different industries and sectors. The goal is to establish a common ground that 
supports the diverse characteristics of individual data spaces while fostering an integrated ecosystem where data can be 
a fluid, powerful asset across the entire digital landscape.




## FIWARE and iSHARE Technology Building blocks

This section describes the different FIWARE open source components which can be combined with iSHARE services and used under 
iSHARE-compliant governance frameworks for building data spaces. These components can be integrated to build the data space 
connectors participants need to deploy for connecting to the data space or can be used for building intermediary services like 
data publication platforms or marketplaces.

For convenience, we will be referring to data spaces powered by the combination of FIWARE and iSHARE building blocks as 
i4Trust data spaces.

The description of FIWARE and iSHARE building blocks for data spaces and the specification of flows linked to interaction 
among them can be found in the following document:

## i4Trust Building Blocks Document

> :information_source: **i4Trust Building Blocks Document**  
>
> *Download: [:arrow_down:](https://i4trust.github.io/building-blocks/docs/i4Trust-BuildingBlocks_v4.0.pdf)
> (Version 4.0, 02/2023)*




### Data Interoperability

#### Data Exchange API

Data providers joining data spaces must be able to publish data resources at well defined endpoints knowing that data consumers, 
unknown by them a priori, will know how to retrieve and consume data through those endpoints. Data consumers, on the other 
hand, must know how data available through endpoints they discover can be consumed. This is achieved by adopting domain-agnostic 
common APIs for data exchange.

In i4Trust data spaces, participants are expected to exchange digital twin data, that is the values of attributes characterizing 
entities representing physical world objects (e.g., a street, a room within a floor of a building, a vehicle) or real world 
concepts (e.g., a trouble ticket, an alarm).

The **NGSI API** is the API used in i4Trust data spaces for the exchange of digital twin data. Many different systems have been developed 
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
In the current release of i4Trust, PEP and PDP functionalities are provided via libraries in [lua](https://github.com/FIWARE/lua-fiware-lib). The libraries can be used to implement plugins for various api-gateways, with a solution for the [Kong API-Gateway](https://github.com/Kong/kong) already [implemented by FIWARE](https://github.com/FIWARE/kong-plugins-fiware).
The PDP functionality for authorization via VerifiableCredentials is provided as an additional component, the [DSBA-PDP](https://github.com/FIWARE/dsba-pdp) and can be integrated into the flow, using the same [Kong-Plugins](https://github.com/FIWARE/kong-plugins-fiware) as PEP.
The [DSBA-PDP](https://github.com/FIWARE/dsba-pdp) uses the [EBSI Trusted Issuers Registry API](https://api-pilot.ebsi.eu/docs/apis/trusted-issuers-registry/latest#/) for evaluating if an issuer is allowed to issue certain credentials. The PDP provides a compatibility mechanism to use the [iShare delegation endpoint](https://dev.ishare.eu/delegation/endpoint.html) as trusted issuers source. Additionally, the [iShare delegation endpoint](https://dev.ishare.eu/delegation/endpoint.html) is used to evaluate the actual policies referenced by the roles in the received credential.

In addition, [Keyrock](https://github.com/ging/fiware-idm) also implements Policy Administration Point (PAP) and Policy 
Management Point (PMP) standard [XACML](https://en.wikipedia.org/wiki/XACML) functions.

For defining access policies, iSHARE brings the 
[delegation evidence data model](https://dev.ishare.eu/delegation/delegation-evidence.html) which is structured according 
to a JSON port of 
the XACML standard. A key functionality of iSHARE is delegating rights to another party, authorising them to act on your behalf. 
In that sense, a delegation evidence expresses the delegation of rights from a delegator to the delegate . Rights are expressed in 
rules in terms of allowed actions to be performed on resources, under the licenses as defined in policySets.

Authorization capabilities through the SIOP-2/OIDC4VP flow are provided by [VCBackend](https://github.com/FIWARE/VCBackend) and [VCWaltid](https://github.com/FIWARE/VCWaltid). The combination of both can be used as issuer of VerfiableCredentials and as a verifier, creating [JWT's](https://jwt.io/) to access the backend secured by the [Kong-PEP](https://github.com/FIWARE/kong-plugins-fiware) and the [DSBA-PDP](https://github.com/FIWARE/dsba-pdp). A minimal wallet for storing the credentials is provided by the [VCWallet](https://github.com/FIWARE/VCWallet).



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


### Marketplace

Marketplace intermediary services can be based on the FIWARE Business API Ecosystem (BAE) which allows service providers to publish offerings
around data assets, and service consumers to acquire access to them. A full instance is based on the BAE itself, the
Keyrock Identity Manager and several databases. These
[instructions](https://github.com/i4Trust/tutorials/tree/main/PacketDelivery-ReferenceExample/i4Trust-Marketplace) describe how to deploy a
full setup on Kubernetes.
