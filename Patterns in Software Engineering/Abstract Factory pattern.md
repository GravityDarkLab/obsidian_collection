It is a [[Creational patterns]].

The Abstract Factory pattern is a creational design pattern that provides an interface for creating families of related or dependent objects without specifying their concrete classes. ==The pattern defines a factory interface that the client code uses to create objects==, but the concrete classes of the objects are determined by concrete factory classes.

The main idea behind the Abstract Factory pattern is to encapsulate the process of creating objects in a separate class, so that the client code does not need to know about the specific classes of the objects that it creates. Instead, the client code only needs to know about the factory interface and the interface of the objects that it creates.

```java
interface Burger {
    public String getDescription();
}

class ClassicBurger implements Burger {
    @Override
    public String getDescription() {
        return "Classic burger with beef patty, lettuce, tomato, cheese and ketchup";
    }
}

class VeggieBurger implements Burger {
    @Override
    public String getDescription() {
        return "Veggie burger with vegetable patty, lettuce, tomato, cheese and ketchup";
    }
}

interface BurgerFactory {
    public Burger createBurger();
}

class ClassicBurgerFactory implements BurgerFactory {
    @Override
    public Burger createBurger() {
        return new ClassicBurger();
    }
}

class VeggieBurgerFactory implements BurgerFactory {
    @Override
    public Burger createBurger() {
        return new VeggieBurger();
    }
}
```
The client code can use the factory method to create burgers, without knowing the specific classes of the burgers that it creates. It only needs to know about the `BurgerFactory` interface and the interface of the burgers that it creates.
```java
class BurgerStore {
    public static void main(String[] args) {
        BurgerFactory classicFactory = new ClassicBurgerFactory();
        Burger classicBurger = classicFactory.createBurger();
        System.out.println("Classic burger: " + classicBurger.getDescription());

        BurgerFactory veggieFactory = new VeggieBurgerFactory();
        Burger veggieBurger = veggieFactory.createBurger();
        System.out.println("Veggie burger: " + veggieBurger.getDescription());
    }
}
```

See [[Factory vs Abstract Factory]].