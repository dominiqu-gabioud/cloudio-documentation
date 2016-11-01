# Features #

> **cloud.iO** A practicable open source framework for IoT.

## cloud.iO and IoT ##

[Internet of Things (IoT)](https://en.wikipedia.org/wiki/Internet_of_things) covers a large variety of themes:

- **Various connected devices:** Hearing aids, hydro power plants, pet animals, oil tanks, flower pots...
- **Various applications:** Monitoring and dashboards, safety and alarming (people, animals,  appliances, buildings...), process optimisation, entertainement...
- **Various technologies:** Embedded systems, wireless networks, data security, semantics, cloud, databases, big data...

cloud.iO implements the layer at the heart of an IoT system: it provides an interface for  devices and another interface for applications. Hence applications and devices are decoupled  from each other.
cloud.iO is independant of application domains, networking technologies, semantics and data processing frameworks.

## IoT architecture overview ##

Despite the extreme diversity of devices, applications and techologies, IoT is based on a unique pattern illustrated in the figure below:

![Architecture of an IoT ecosystem](figs/logo.png)

Elements of an IoT ecosystem are:

- **Field devices** connected to "things".
- **Communication networks** connecting field devices to the cloud, possibly through intermediate gateways.
- **Databases** storing:
	- the current state and status of the IoT world,
	- the access rights (see below), and
	- historical values.
- **Applications** which are processing field data and possibly also controlling field devices.
- **Users**: persons or entities (e.g. companies) owning field devices and granting applications read / write access to their field devices.

## About cloud.iO ##

cloud.iO lies at the core of an IoT ecosystem. It is the switchboard upon which field devices, applications and databases are connected.

cloud.iO is based on proven and powerful internet components, which have been complemented by a limited set of mostly independent and stateless micro-services.

Security and privacy issues have been considered since the early design of cloud.iO:

- Devices are authenticated and their connection to the cloud is encrypted.
- A central access control system let field device owners decide which applications have read and write access to what field data.


## The cloud.iO components ##


The heart of cloud.iO is **[the robust messaging system RabbitMQ](https://www.rabbitmq.com/)**. It has been complemented to support access control (see [https://github.com/cloudio-project/cloudio-rabbitmq](https://github.com/cloudio-project/cloudio-rabbitmq)).

Databases are not part of the cloud.iO framework. However cloud.iO provides backend APIs to interface three databases:

1. an **history database** to store past monitoring and control data,
2. a so-called **process database**, with the current topology and data model of connected endpoints, and
3. an **access right database**.

In its reference implementation, cloud.iO provides interface to two database management systems:

- the **[InfluxdB time series database](https://influxdata.com)** acting as history database, and
- the **[NoSQL document database MongodB](http://mongodb.com)** supporting the process and access right databases.

The actual cloud.iO functions are implemented by so-called **micro-services**, which links the messaging system to external components like field devices, application, databases and management interfaces. cloud.iO micro-services are build with the **[Spring IO platform](http://http://spring.io/)**.

**Field devices** are named "**cloud.iO endpoints**": The communication between endpoints ant the core cloud.iO is based on a secure version of **[the light-weight messaging protocol MQTT](http://mqtt.org)**.

Libraries for cloud.iO endpoints have been developed on the basis of the **[paho  MQTT libraries](http://eclipse.org/paho)**.

## Online documentation ##

- **cloud.iO semantics**: field device information model, message and topic specification.
- **cloud.iO message routing concept**: topic based routing of messaging, subscribtion service
- **cloud.iO security model**: authentication, access control, ciphering, privacy rules .enforcment
- **cloud.iO endpoints**: simplifying the developement of cloud.iO field devices thanks to the cloud.iO endpoint libraries and their APIs.
- **cloud.iO applications**: simplifying the developement of cloud.iO application thanks to the cloud.iO application libraries and their APIs.
- **cloud.iO backend APIs for databases**: Backend API for history, process and access right databases.


- web: [http://cloudio.hevs.ch](http://cloudio.hevs.ch)
- github: [https://github.com/cloudio-project](https://github.com/cloudio-project)

- **Bold** (`Ctrl+B`) and *Italic* (`Ctrl+I`)
- Quotes (`Ctrl+Q`)
- Code blocks (`Ctrl+K`)
- Headings 1, 2, 3 (`Ctrl+1`, `Ctrl+2`, `Ctrl+3`)
- Lists (`Ctrl+U` and `Ctrl+Shift+O`)

