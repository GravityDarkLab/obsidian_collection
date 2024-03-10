It is an [[Architectural patterns]].

- The layered architectural style is a design pattern that organizes the functionality of an application into a set of layers or tiers, each of which has a specific responsibility. The layers are arranged in a hierarchy, with the lower layers providing services to the higher layers.

- A common example of a layered architecture is the three-tier architecture, which is composed of a presentation layer, a business logic layer, and a data access layer:
	- **The presentation layer**: is responsible for displaying the user interface and handling user input.
	- **The business logic layer**: is responsible for implementing the business logic and validating the data.
	- **The data access layer**: is responsible for interacting with the database and performing CRUD (Create, Read, Update, Delete) operations on the data.

Each layer communicates with the layer immediately below it and it can use the services provided by the lower layer without knowing the details of their implementation.

> A **<u>Layer</u>** is a **type** (e.g. class, subsystem) and **<u>tier</u>** is an **instance** (e.g. object, hardware no

## Closed architecture:
![[Bildschirm­foto 2023-01-24 um 18.33.54.png]]

## Open architecture:
![[Bildschirm­foto 2023-01-24 um 18.34.10.png]]