It is a [[Structural Pattern]].

- **Problem**: there are hierarchies with arbitrary depth and width (e.g. folders and files).
- **Solution**: the composite pattern lets a Client treat an individual class called Leaf and Compositions of Leaf classes uniformly

> The Composite pattern is used when you want to represent a hierarchical structure of objects. It provides a way to treat individual objects and compositions of objects uniformly. The composite object contains a collection of other objects, which can be either leaf objects or other composite objects. This allows you to build complex structures by recursively composing objects. 

- The Composite pattern is a structural pattern that allows you to compose objects into tree-like structures and treat individual objects and compositions of objects uniformly. This pattern is often used to represent hierarchical structures such as file systems, organizational charts, and other tree-like structures.
- **Examples**:
	1.  **File system:** A file system is a classic example of a hierarchical structure, where a folder can contain other folders (composite) and files (leaf). The composite pattern can be used to represent this structure, where a folder is a composite object that can contain other folders and files as its children. The `add` and `remove` methods can be used to add and remove files and folders, and the `operation` method can be used to perform common operations such as copying or moving files and folders.
	2.  **Organizational charts:** Another example of a hierarchical structure is an organizational chart, where an organization is composed of departments (composite) and employees (leaf). A department can contain other departments and employees, and the composite pattern can be used to represent this structure.
	3.  **Graphics editor:** In a graphics editor, you might have objects like lines, circles, and rectangles, where a group of objects can be a composite object made up of other objects. This way, you can move and resize the group of objects together, as well as perform other operations on the group as a whole.
	4.  **GUI frameworks:** Many GUI frameworks use the composite pattern for building the layout of a window or dialog. The layout manager object is a composite object that contains other layout manager objects or leaf objects (like buttons, labels, text fields, etc.).

## Code Example:

```java
interface Graphic {
    public void move(int x, int y);
    public void draw();
    public void add(Graphic graphic);
    public void remove(Graphic graphic);
}

class Line implements Graphic {
    private int x1, y1, x2, y2;

    public Line(int x1, int y1, int x2, int y2) {
        //create
    }

    public void move(int x, int y) {
        //move
    }

    public void draw() {
        // code to draw a line
    }

    public void add(Graphic graphic) {
        // not implemented
    }

    public void remove(Graphic graphic) {
        // not implemented
    }
}

class Circle implements Graphic {
    private int x, y, r;

    public Circle(int x, int y, int r) {
        //create
    }

    public void move(int x, int y) {
       //move
    }

    public void draw() {
        // code to draw a circle
    }

    public void add(Graphic graphic) {
        // not implemented
    }

    public void remove(Graphic graphic) {
        // not implemented
    }
}
```

![[Bildschirm­foto 2023-01-23 um 22.20.27.png]]