It is a [[Behavioral patterns]].

- **Problem**: different algorithms exist for a specific task.
- **Examples of specific tasks**:
	- Different ways to sort a list (bubble sort, merge sort, quick sort).
	- Different collision strategies for objects in video games.
	- Different ways to parse tokens into an abstract syntax tree (bottom-up, top-down).
- If we need a new algorithm, we want to add it without changing the rest of the application or the other algorithms.
- **Solution**: the strategy pattern **allows to switch between different algorithms at run time** based on the context and a policy.
![[Bildschirm­foto 2023-01-24 um 17.47.18.png]]
![[Bildschirm­foto 2023-01-24 um 17.47.53.png]]


## Code example:
```java
interface PaymentStrategy {
    void pay(double amount);
}
class CreditCardPayment implements PaymentStrategy {
    private String name;
    private String cardNumber;
    private String cvv;
    private String dateOfExpiry;

    public CreditCardPayment(String nm, String ccNum, String cvv, String expiryDate){
        this.name=nm;
        this.cardNumber=ccNum;
        this.cvv=cvv;
        this.dateOfExpiry=expiryDate;
    }

    public void pay(double amount) {
        System.out.println(amount + " paid with credit/debit card");
    }
}
class PayPalPayment implements PaymentStrategy {
    private String emailId;
    private String password;

    public PayPalPayment(String email, String pwd){
        this.emailId=email;
        this.password=pwd;
    }

    public void pay(double amount) {
        System.out.println(amount + " paid using PayPal.");
    }
}
class ShoppingCart {
    List<Item> items;
    PaymentStrategy paymentMethod;
    
    public void setPaymentMethod(PaymentStrategy paymentMethod) {
        this.paymentMethod = paymentMethod;
    }
    public void pay() {
        double total = calculateTotal();
	    paymentMethod.pay(total);
	}
	private double calculateTotal() {
	    double sum = 0;
	    for (Item item : items) {
	        sum += item.getPrice();
	    }
	    return sum;
	}
}
```

In this example, the `ShoppingCart` class is the client that wants to execute the payment algorithm. It has a reference to a `PaymentStrategy` interface, which defines the contract for the payment algorithm. The `CreditCardPayment` and `PayPalPayment` classes are the concrete strategies that implement the `PaymentStrategy` interface, providing different algorithms for paying with a credit card or PayPal.

The client can use the `setPaymentMethod` method to set the desired payment strategy, for example:
```java
ShoppingCart cart = new ShoppingCart();
cart.setPaymentMethod(new PayPalPayment("user@example.com", "password"));
```

When the `pay` method is called, it calculates the total amount and then uses the `pay` method of the selected payment strategy to execute the algorithm.

> In this example, the strategy pattern allows the client to choose the payment method at runtime and encapsulate the payment algorithm in a separate class, making it interchangeable and easy to change or extend.