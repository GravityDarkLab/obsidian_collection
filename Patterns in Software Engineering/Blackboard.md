it is an [[Architectural patterns]].

The blackboard pattern is an architectural pattern that is often used in artificial intelligence and other complex systems. It is based on the idea of a central "blackboard" that holds all of the information that is needed by the different components of the system. The different components can access the blackboard to read and write information, but they don't communicate directly with each other. Instead, they interact with the blackboard, which acts as an intermediary.

The blackboard pattern is useful in systems where there are many different components that need to share information, but there is no clear hierarchy of which component should be in charge of the information. The blackboard provides a centralized location for the information, and it is the responsibility of the individual components to read and write the information as needed.

## Component:
- **Blackboard**: is the repository for the problem, partial solutions, and new information (hypotheses,…). --> **knowledge sharing area**.
- **Knowledge sources**: read anything that is placed on the blackboard and place new information created by them on the blackboard. --> **Expert**.
- **Control**: governs the flow of the problem solving activity in the system: how knowledge sources are notified of new information on the blackboard --> **Supervisor**.

## Steps to realize the Blackboard
1. Define the problem (make sure there is no algorithmic solution for the problem):
	- Identify the application domain and specify the requirements.
	- Identify the actors (in particular the end user).
2. Define the solution space:
	- Specify top level and intermediate solutions (for higher and lower abstraction levels).
	- Identify partial/complete solution candidates: a complete solution solves the problem, partial solutions solve parts of the problem.
3. Identify the knowledge sources (KS): Identify their input and outputs.
4. Define the blackboard: identify all the representations that are needed to allow the KSs to read from and contribute to the blackboard (not every KS needs to understand every representation!).
5. Define the control: implement the problem-solving strategy (Who can construct hypotheses? Who decides the credibility of hypotheses? Who decides what is an acceptable solution?)
6. mplement the knowledge sources (KS):
	- Split each KS into a condition part and an action part.
	- Use different technologies: rule based systems, neural networks, in fact any computational intelligence method, but also conventional procedures/functions

## Example:
![[Bildschirm­foto 2023-01-27 um 22.15.33.png]]![[Bildschirm­foto 2023-01-27 um 22.16.50.png]]

## Code example:
> Consider a system that is responsible for recognizing objects in an image. The system is made up of several different components, each responsible for a different step in the process. There's a component that detects edges in the image, another that detects shapes, another that recognizes individual objects, and so on.
```java
class Blackboard {
    private Image image;
    private List<Edge> edges;
    private List<Shape> shapes;
    private List<Object> objects;
    // ... other data as needed
    
    public Blackboard(Image image) {
        this.image = image;
    }
    
    public void setEdges(List<Edge> edges) {
        this.edges = edges;
    }
    public List<Edge> getEdges() {
        return edges;
    }
    public void setShapes(List<Shape> shapes) {
        this.shapes = shapes;
    }
    public List<Shape> getShapes() {
        return shapes;
    }
    public void setObjects(List<Object> objects) {
        this.objects = objects;
    }
    public List<Object> getObjects() {
        return objects;
    }
    // ... other getters and setters as needed
}
```
In this example, the Blackboard class holds all the information that is needed by the different components of the system. The EdgeDetection component reads the image from the blackboard and writes the detected edges back to the blackboard. The ShapeDetection component reads the edges from the blackboard and writes the detected shapes back to the blackboard, and so on. ==Each component is only concerned with the information that it needs, and it doesn't need to know about the other components==.

Here's an example of how a component might use the blackboard:
```java
class EdgeDetection {
    public void detectEdges(Blackboard blackboard) {
        // Read the image from the blackboard
        Image image = blackboard.getImage();
        // Perform edge detection on the image
        List<Edge> edges = ...;
        // Write the edges back to the blackboard
        blackboard.setEdges(edges);
    }
}
```
In this way, the blackboard acts as a central hub for all the information that is needed by the different components of the system, and it allows the components to work independently of each other.
