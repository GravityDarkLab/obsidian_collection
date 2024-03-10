It is a [[Structural Pattern]].

The Flyweight pattern is a structural design pattern that provides a way to efficiently manage large numbers of similar objects. It is used to minimize the number of objects that need to be created and managed by the program by sharing objects that are identical or similar.

The Flyweight pattern works by dividing the objects into two types: shared and unshared. The shared objects are stored in a flyweight factory, where they can be reused by multiple clients. The unshared objects are stored in the client code and contain the state that is unique to each instance of the object.

## Check-list:
- Ensure that object overhead is an issue: the client of the class is able and willing to absorb responsibility realignment.
- Divide the target class's state into 2 objects:** shareable intrinsic state** and **non-shareable extrinsic state**.
- Remove the non-shareable state from the class attributes, and add it to the calling argument list of affected methods.
- Create a factory that can cache and reuse existing class instances.
- The client must use the factory instead of the new operator to request objects.
- The client must look-up or compute the non-shareable state, and pass that state to class methods.

## Code example:
```java
interface Bullet {
    public void fire(int x, int y);
}
class ConcreteBullet implements Bullet {
    private int damage;
    private int speed;
    public ConcreteBullet(int damage, int speed) {
        this.damage = damage;
        this.speed = speed;
    }
    @Override
    public void fire(int x, int y) {
        // Perform the bullet fire using the damage and speed
    }
}
class BulletFactory {
    private Map<String, Bullet> bullets = new HashMap<>();
    public Bullet getBullet(String type) {
        Bullet bullet = bullets.get(type);
        if (bullet == null) {
            if (type.equals("normal")) {
                bullet = new ConcreteBullet(10, 20);
            } else if (type.equals("super")) {
                bullet = new ConcreteBullet(20, 30);
            }
            bullets.put(type, bullet);
        }
        return bullet;
    }
}
class Player {
    private BulletFactory bulletFactory;
    public Player(BulletFactory bulletFactory) {
        this.bulletFactory = bulletFactory;
    }
    public void fire(String bulletType, int x, int y) {
        Bullet bullet = bulletFactory.getBullet(bulletType);
        bullet.fire(x, y);
    }
}
```
In this example, the `Bullet` interface defines the interface for the bullet objects, and the `ConcreteBullet` class is a concrete implementation of the `Bullet` interface. The `BulletFactory` class is responsible for creating and managing the bullet objects. **It stores the bullet objects in a map, where they can be reused by multiple players**.

The `Player` class uses the factory to create the bullet object and fire it, the factory is responsible for creating the bullet object and reuse it if it already exists.

This example shows how the Flyweight pattern can be used to manage a large number of similar objects, such as the bullets in a game. By using the Flyweight pattern, we can minimize the number of objects that need to be created and managed by the program, which can improve the performance of the game. It's also important to note that this pattern can be extended to other game objects like enemies, items, etc.
