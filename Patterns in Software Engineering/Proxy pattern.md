It is a [[Structural Pattern]].

- **Problem**: the object is complex, its instantiation is expensive.
- **Solution**: 
	- Delay the instantiation until the object is actually used.
	- If the object is never used, then the costs for its instantiation do not occur.	
 - **Problem**: the object is located on another node (i.e. on a web server), accessing the object is expensive.
 - **Solution**: 
	 - Instantiate and initialize a “smaller” local object, which acts as a representative (“proxy”) for the remote object.
	 - Try to access mostly the local object.
	 - Access the remote object only if really necessary


The Proxy pattern is a structural pattern that provides a surrogate or placeholder object that controls access to another object, called the subject. The proxy can be used to add behavior before or after the subject's methods are invoked, or to provide a different implementation of a subject's methods.
![[Bildschirm­foto 2023-01-23 um 23.08.02.png]]


- The Proxy pattern can be used in situations where:
	1.  **Remote access:** The subject is located in a remote location and the proxy is used to provide a local representation of the subject.
	2. **Substitute (virtual proxy)**: the proxy object acts as a stand-in for an object which is expensive to create or download
	3.  **Access control:** The proxy is used to control access to the subject, such as checking if the client is authorized to access the subject.
	4.  **Lazy initialization:** The proxy is used to delay the initialization of the subject until it is actually needed.
	5.  **Caching:** The proxy is used to cache the results of the subject's methods, so that they do not have to be recalculated every time they are invoked.
![[Bildschirm­foto 2023-01-23 um 23.12.51.png]]

## Advantages:
- The proxy pattern allows to defer object creation and object initialization to the time the object is needed.
- Reduces the cost of accessing objects.
- The proxy acts as a stand-in for the real object.
- The proxy creates the real object only if the user asks for it.
- Provides location transparency


## Code Example:
```java
interface Image {
    public void display();
}

class RealImage implements Image {
    private String fileName;

    public RealImage(String fileName) {
        this.fileName = fileName;
        loadFromDisk(fileName);
    }

    private void loadFromDisk(String fileName) {
        System.out.println("Loading " + fileName);
    }

    public void display() {
        System.out.println("Displaying " + fileName);
    }
}

class ProxyImage implements Image {
    private RealImage realImage;
    private String fileName;

    public ProxyImage(String fileName) {
        this.fileName = fileName;
    }

    public void display() {
        if (realImage == null) {
            realImage = new RealImage(fileName);
        }
        realImage.display();
    }
}
```


