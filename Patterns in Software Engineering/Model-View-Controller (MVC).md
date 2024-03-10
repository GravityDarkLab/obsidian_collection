It is an [[Architectural patterns]].

`Problem: in systems with high coupling any change to the boundary objects (user interface) often forces changes to the entity objects (data).`
`Solution: decouple data access (entity objects) and data presentation (boundary objects)`


The Model-View-Controller (MVC) pattern is a design pattern used in software engineering to separate the logic of a program into three interconnected components: the model, the view, and the controller.

-   **The Model**: represents the data and the business logic of the program. It is responsible for retrieving and storing data, and for performing any calculations or processing that is required.
-   **The View** represents the user interface of the program. It is responsible for displaying the data to the user and for handling user input.
-   **The Controller** acts as a mediator between the model and the view. It is responsible for receiving input from the user, updating the model accordingly, and then updating the view to reflect any changes in the model.

A simple example of an MVC pattern for a weather app using Java would be as follows:

-   The model would contain classes such as `WeatherData` and `WeatherService` that retrieve and store weather information from an API.
-   The view would contain classes such as `WeatherView` and `WeatherGraph` that display the current weather information and forecast in a graphical format.
-   The controller would contain a class such as `WeatherController` that would handle user input, update the model with new data, and update the view to reflect any changes in the weather information.
![[Bildschirm­foto 2023-01-26 um 17.00.18.png]]

> View and Controller observe the Model (subject/ observable) so that they get notified of any change in the model.
> **They subscribe**.

## Pull notification variant:

==**View and controller obtain the data from the model**==.
![[Bildschirm­foto 2023-01-26 um 17.10.45.png]]

## Push notification variant:
- ==**The model sends the changed state to view and controller**==.
![[Bildschirm­foto 2023-01-26 um 17.11.14.png]]