# Universal Software Carbon Measurement (USCM) API  – PRF

**_USCM is a working title, it will <span style="text-decoration:underline;">not </span>be released under that name._**

_Define Once, Measure Everywhere._

If you can’t measure, you can’t improve. Unfortunately, measuring software carbon emissions is complex and very nuanced; only some people know how to do it well. However, measuring is the biggest bottleneck to reducing the software industry's carbon emissions, so during COP28, the Green Software Foundation announced the launch of USCM. One model to measure everything, everywhere. 


## Problems

Modern applications are composed of many smaller pieces of software (components) running on many different _environments_, for example, private cloud, public cloud, bare-metal, virtualized, containerized, mobile, laptops, and desktops.

Every _environment_ requires a different way of measurement, and there is no _single_ solution you can use to calculate the carbon emissions for all environments. 

Measuring requires data. There are free publicly available data sources and higher quality commercial or private data sets. Combining them properly requires a deep understanding of methodologies.

The friction to measuring software emissions isn't that we need to know how, it's that we run software on many _things_ and each _thing_ has several different ways to measure.

There are also two broad categories of measurement, **measurement for reporting** (e.g. GHG) and **measurement for action** (e.g. SCI). Measuring for action requires different measurement methodologies than measuring for reporting.

The number of people worldwide with the expert knowledge to make the above distinctions is tiny.


## Solution

Therefore, the Green Software Foundation created USCM, a single API that you can use to measure your software emissions for every runtime environment. So if your application runs on bare-metal servers in the private cloud, virtualized servers in the public cloud, mobile, desktop, and laptop end-user devices, the USCM gives you data for all of them.

The USCM is:

* **Opinionated**: It’s the expertise in software measurement codified into software. Rather than giving you options, it gives you answers.
* **Ubiquitous**: Whatever the environment, bare metal, virtualized, mobile, IoT, USCM will always be able to give you numbers.
* **Declarative**: You express your intentions, needs, and context, and USCM selects the correct measurement methodology. For example, if you are calculating an SCI score, the USCM will return you data that meets the requirements of the SCI. Likewise, if you are calculating for GHG reporting, the USCM will return you information that meets the requirements of GHG reporting.
* **Free**: The USCM is open source and comes linked with public data sources that are free to use. Using the library doesn't cost anything; however, the free sources might be limited.
* **Extendable**: The USCM can be enhanced to leverage more advanced commercial or private models, for example, real-time electricity carbon intensity feeds.

## Audience

* Software monitoring products looking to add carbon as a software measurement metric.
* Software optimization tools looking to represent optimizations in terms of carbon reductions.
* Developer tooling. Developer and Dev/Ops focussed products looking to add carbon measurement.
* Sustainability professionals who are interested in calculating the carbon emissions for reporting.
* Organizations looking to measure-for-action the carbon emissions reduction from migrating a software application from on-prem to the cloud. 

# FAQ

## What are the non-functional requirements of the USCM?

* The default/free version of the USCM has complete coverage across the universe of options. It might not give you the most accurate numbers but it gives you numbers for every runtime environment, device type, usage pattern.
* USCM can be extended with private/commercial data. This doesn't increase coverage, this increases accuracy and specificity.
* The more context you provide the USCM, the more accurate estimates it can provide. 

## What might an architecture diagram for the USCM look like?

The USCM acts like a facade, it might call out to other APIs, CSV files, DBs, the underlying model can be of any format and in any location. 

The USCM provides a common interface to all the various models, makes opinionated decisions about which model to use and how its results should be transformed into the format you need for your calculations.

![image](https://user-images.githubusercontent.com/897523/210799000-3e20bdd7-98f7-409d-b70e-06fc5d954e95.png)

## What could an interface be for the USCM?

_This is a proposal to drive discussion, lots of room for change on how to implement this._

There are three inputs to the USCM, the Context, Key and Usage.

* The Context helps determine the type of methodology we are calculating for, e.g. SCI or GHG and the types of outputs we are looking for.
* The Key helps determine which model to use. 
* The Usage contains inputs that are passed to the model, e.g. some measure of volume of usage, e.g. length of time, GB transferred.

The USCM returns estimates for Carbon emissions and where it makes sense a breakdown of the Carbon into  Energy (E), Embodied Carbon (M) and Carbon Intensity of Electricity (I).

## How could the USCM resolve a request to a particular model?

_This is a proposal to drive discussion, lots of room for change on how to implement this._

The more data you provide in the query the more accurate a model that USCM will be able to choose, for example:

**ModelKey**: DEVICE/LAPTOP

Would resolve to a generalised model that gives numbers for an average laptop (you might choose this key if you had no data regarding the model of the laptop you are using)

**ModelKey** DEVICE/LAPTOP

**Context**: { MEM: 1TB, DISK: 500GB, SPEED: 3GHz }

Would resolve to a generalized model for laptops with around 1TB mem, 500gb SSD and with a 3GHz CPU. You might choose this if you don’t know the model of laptop but have data regarding its specification.

**ModelKey** DEVICE/LAPTOP/HP

**Context**: { MODEL: ELITEBOOK }

Would resolve to a specific model for a HP laptop.


## Can you give some concrete examples of how to use the USCM to ask specific types of questions?

_This is a proposal to drive discussion, lots of room for change on how to implement this._


### SaaS Database

**ModelKey:** SERVICE/DB/AWS/DYNAMODB

**Usage**: { SIZE: 4GB }

**Outputs**: { C: Xg }

If our install has a specific model for AWS/DYNAMODB then we will use that model. If our install doesn't’ have a model for AWS/DYNAMODB it would resolve to a generic model for SaaS DBs (SERVICE/DB)

For things like services SaaS products we’d expect the models to just return estimates of carbon emissions.


### Public Cloud Virtual Machine

**ModelKey:** SERVICE/VM/AZURE/DSV3

**Usage**: { Utilization: 50% }

**Outputs**: { C: X g, E: X Wh, I: _X_ gCO2e/kWh, M: _X_ g }

If our install has a specific model for Azure then we will use that model (SERVICE/VM/AZURE/). If our install doesn't’ have a model for SERVICE/VM/AZURE it would resolve to a generic model for VMs (SERVICE/VM)


### Network Requests

**ModelKey:** SERVICE/NETWORK/MOBILE/4G

**Usage**: { Size: 4GB }

**Outputs**: { C: X g }

If our install has a specific model for 4G networks then we will use that model (SERVICE/NETWORK/MOBILE/4G). If our install doesn't’ have a model for SERVICE/NETWORK/MOBILE/4G it would resolve to a generic model for Networking (SERVICE/NETWORK)


## What technology might we use for implementing this project?

_This is a proposal to drive discussion, lots of room for change on how to implement this._

There seem to be lots of similarities between what's being proposed here and [GraphQL](https://graphql.org/). 

* GraphQL acts like a facade query language which can sit over a collection of databases, other APIs etc… and give them all a common interface. 
* Works with unstructured data which a lot of our models will have, or at least every model we incorporate might have a different structure.
* Large ecosystems of developers who understand GraphQL and mature developer tooling.
