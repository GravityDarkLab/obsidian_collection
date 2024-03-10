It is a [[Structural Pattern]].

`must interface to an existing set of objects, must interface to an existing API, must interface to an existing service`.

- The Facade pattern is a structural pattern that provides a simplified interface to a complex subsystem. It is often used to **hide the complexity of a system** and provide a simpler, more user-friendly interface.
- The Facade pattern typically consists of a ==Facade class==, which provides a **simplified interface** to a complex subsystem, and a set of classes that make up the subsystem. 
- The Facade class **delegates** requests from the client to the appropriate classes within the subsystem. This allows the client to interact with the system through a single, simplified interface, rather than having to interact with the subsystem directly.

> The Facade pattern is used when you want to provide a simplified interface to a complex subsystem. It is used to hide the complexity of the subsystem and provide a single, simplified entry point for the client to interact with the subsystem. The Facade class typically delegates requests from the client to the appropriate classes within the subsystem, allowing the client to interact with the subsystem through a single, simplified interface.

## Code Example:

```java
class Order {
    private int id;
    private List<Item> items;
    private float total;

    public Order(int id, List<Item> items, float total) {
        //initi...
    }

    //Add getter and Setter
}

class Item {
    private int id;
    private String name;
    private float price;

    public Item(int id, String name, float price) {
        //init
    }

    //Add getter and Setter
}

class OrderService {
    public Order createOrder(List<Item> items) {
        // Code to create an order in the database
        int id = generateOrderId();
        float total = calculateTotal(items);
        return new Order(id, items, total);
    }

    public void processPayment(Order order, PaymentMethod paymentMethod) {
        // Code to process payment for the order
    }

    public void sendConfirmationEmail(Order order) {
        // Code to send confirmation email for the order
    }
}

class PaymentMethod {
    private int id;
    private String name;

    public PaymentMethod(int id, String name) {
        //init
    }

    //Add getter and Setter
}

class OrderFacade {
    private OrderService orderService;

    public OrderFacade(OrderService orderService) {
        this.orderService = orderService;
    }

    public Order placeOrder(List<Item> items, PaymentMethod paymentMethod) {
        Order order = orderService.createOrder(items);
        orderService.processPayment(order, paymentMethod);
        orderService.sendConfirmationEmail(order);
        return order;
    }
}

class Client {
    public static void main(String[] args) {
        List<Item> items = new ArrayList<>();
        items.add(new Item(1, "item 1", 10));
        items.add(new Item(2, "item 2", 20));
        PaymentMethod paymentMethod = new PaymentMethod(1, "Visa"); 
        OrderService orderService = new OrderService(); 
        OrderFacade orderFacade = new OrderFacade(orderService);
        Order order = orderFacade.placeOrder(items, paymentMethod);
        System.out.println("Order placed successfully with id:"+order.getId());
    
    }
}
```

## Advantages:
The Facade pattern has several advantages:

1.  **Simplifies the interface:** The Facade pattern provides a simplified interface to a complex subsystem, making it easier for clients to use the subsystem.    
2.  **Hides the complexity of the subsystem:** The Facade pattern hides the complexity of the subsystem from the client, which can make it easier for the client to understand the system.    
3.  **Promotes loose coupling:** The Facade pattern reduces coupling.
4.  **Single Responsibility Principle:** The Facade pattern can help to adhere to the Single Responsibility Principle, by keeping the subsystem classes focused on their specific responsibilities and delegating the responsibilities of providing a simplified interface to the Facade class.
5. **Easier to test**.