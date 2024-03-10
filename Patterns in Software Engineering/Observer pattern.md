It is a [[Behavioral patterns]].

- **Problem**: An object that changes its state often.
- **Example**: 
	- a portfolio of stocks.
	- Multiple views of the current state
- **Requirements**:
	- The system should maintain consistency across the (redundant) views, whenever the state of the observed object changes.
	- The system design should be highly extensible.
	- It should be possible to add new views - for example, an alarm - without having to recompile the observed object or existing views.
- **Solution**: model a 1-to-many dependency between objects:
	- Connect the state of an observed object, the subject with many observing objects, and the observers.
- **Benefits**:
	- Maintain consistency across redundant observers.
	- Optimize a batch of changes to maintain consistency.
	- ==Also called Publish and Subscribe==.

> The Observer pattern is a behavioral pattern that allows objects to be notified when the state of another object changes. It defines a one-to-many dependency between objects, where ==one object (the subject)== is **being observed** ==by multiple other objects (the observers)==. When **the state of the subject changes, it notifies all of its observers, who can then update their own state accordingly**.


![[Bildschirm­foto 2023-01-24 um 17.28.35.png]]
![[Bildschirm­foto 2023-01-24 um 17.30.06.png]]

## Code example:
```java
interface Observer {
    void update(Subject subject);
}
interface Subject {
    void registerObserver(Observer observer);
    void removeObserver(Observer observer);
    void notifyObservers();
}

class StockMarket implements Subject {
    private List<Observer> observers = new ArrayList<>();
    private double ibmPrice;
    private double aaplPrice;
    private double googPrice;

    public void registerObserver(Observer observer) {
        observers.add(observer);
    }
    public void removeObserver(Observer observer) {
        observers.remove(observer);
    }
    public void notifyObservers() {
        for (Observer observer : observers) {
            observer.update(this);
        }
    }

    public double getIbmPrice() {
        return ibmPrice;
    }
    public double getAaplPrice() {
        return aaplPrice;
    }
    public double getGoogPrice() {
        return googPrice;
    }
    public void setPrices(double ibmPrice, double aaplPrice, double googPrice) {
        this.ibmPrice = ibmPrice;
        this.aaplPrice = aaplPrice;
        this.googPrice = googPrice;
        notifyObservers();
    }
}

class StockMarketObserver implements Observer {
    private double ibmPrice;
    private double aaplPrice;
    private double googPrice;
    private Subject stockMarket;

    public StockMarketObserver(Subject stockMarket) {
        this.stockMarket = stockMarket;
        stockMarket.registerObserver(this);
    }

    public void update(Subject subject) {
        if (subject instanceof StockMarket) {
            StockMarket stockMarket = (StockMarket) subject;
            this.ibmPrice = stockMarket.getIbmPrice();
            this.aaplPrice = stockMarket.getAaplPrice();
            this.googPrice = stockMarket.getGoogPrice();
            printPrices();
        }
    }

    public void printPrices() {
        System.out.println("IBM: " + ibmPrice + " AAPL: " + aaplPrice + " GOOG: " + googPrice);
    }
}
```
In this example, the `StockMarket` class is the subject and the `StockMarketObserver` class is the observer. The subject maintains a list of its observers and provides methods for registering and unregistering observers. When its state changes, it notifies all of its observers, who can then update their own state accordingly.
The `StockMarketObserver` class is an observer that is interested in being notified when the prices change. When the prices change, the `StockMarket` class calls the `notifyObservers` method, which in turn calls the `update` method on each of the registered observers. In the `update` method, the observer retrieves the new prices from the subject and updates its own state accordingly.

> Another example of the observer pattern is the use of push notifications on mobile devices. A server sends push notifications to multiple clients (observers), notifying them of new updates or events, and each client can update their own state accordingly.

## push pull variances:

The previous example that I provided is an implementation of the Pull Observer pattern. In the pull observer pattern, the observer is responsible for pulling the state that it needs from the subject. The subject provides the observer with the necessary method to retrieve the state. In the example, the `update` method of the observer is pulling the prices of the stocks from the subject by calling the `getIbmPrice()`, `getAaplPrice()` and `getGoogPrice()` methods of the `StockMarket` class.

There is also another type of the observer pattern that is called Push Observer pattern. In this type, the subject pushes the state to the observer by calling the observer's `update(args)` method and passing the new state as an argument. In this pattern, the observer does not need to pull the state from the subject, it will be updated automatically.