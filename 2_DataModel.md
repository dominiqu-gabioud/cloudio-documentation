# Data model #

> **cloud.iO** A framework that lets you define your own data models.  

### About data models ###

In IoT applications, "things" have attributes whose values are mirrored in the cloud and made available to applications. Hence naming conventions are important, so that applications can "understand" the meaning of some variable.

"**Temperature of Room A123 expressed in Kelvin**", "**speed of motor M1 in rpm**", "**Phase 1 RMS current for heat pump HP924**"... These are examples of data model elements that may appear in IoT systems. A common vocabulary and a common meaning for its elements must be be shared by all stakeholders of an IoT system.

As in many frameworks, the data model of an endpoint is organised as a tree: the root is the endpoints itself, leaves are readable and/or writable parameters and branches allow a hiearchical classification of attributes.

### cloud.iO and data models ###

cloudi.iO recognises that each application requires its own data model. Hence:

- The cloud.iO framework has no built-in data models and let IoT application stakeholders define their own data models.
- cloud.iO provides a mean to enforce that a minimal data model is present in a collection of endpoints.

### Structure of the data model for a cloud.iO endpoint  ###

The figure below presents the structure of a cloud.iO endpoint along with an example.

Each cloud.iO endpoint features a unique identifier. Attributes are images of a local variable that can be remotely read or written. Names for nodes, objects and attributes can be basically freely assigned.

Each endpoint, nodes object and attribute features a unique identifier, which is used in the whole cloud.iO framework. 

#### Endpoints IDs ####

An endpoint ID is a globally unique identifier for an endpoint.

#### Nodes ####

A node is basically a container for objects. A node may be required to implement interfaces. An interface defines the minimum set of object classes a given node has to offer. A node may implement any number of interfaces.

The structure of a node may evolve over time: objects can be added or removed dynamically as required.

#### Objects and classes ####

An object is a container for attributes and/or objects. It may conform to zero or one class.

Classes for common object structures enable the reuse of object definitions.

As objects may contain objects, hierarchical structures can be defined. 

#### Attributes ####

Attributes are atomic elements of objects. They are always made up of four fields:

- The **time** field defines the actual type of the attribute:
- The **constraint** defines the actual kind of the attribute:
	- *Static*: A read-only value that never changes. For example manufacturer, model, serial number…
	- *Status*: A read-only value representing a state or a calculated value.
	- *Measure*: Read-only value representing an actual measurement result made by the field device.
	- *Parameter*: A writable configuration parameter of the field device.
	- *SetPoint*: A writable value acting as a set point for a local regulation. Temperature threshold for example.
- The **timestamp** field is the [epoch time](https://en.wikipedia.org/wiki/Unix_time "epoch time") at which the measurement has been taken. The time stamp can be a floating point number is subsecond resolution is needed.
- The **value** field is the actual value of the attribute. It can be either a basic type (int, float, string...) or any JSON element.

