It is an [[Anti-pattern]].

- The Blob antipattern, also known as the "God Object" antipattern, is a software development pattern where a single class or module becomes too large and complex, handling many responsibilities that should be delegated to other classes or modules. This leads to a monolithic and tightly-coupled codebase that is difficult to understand, test and maintain.

- An example of this in Java would be a class that contains a large number of methods and properties that are unrelated to each other. This class would be responsible for many different tasks, making it difficult to understand what it does and how to test it.


> To refactor this pattern, a developer should break down the class into smaller, more focused classes or modules that each have a single responsibility. This will result in a more modular and loosely-coupled codebase that is easier to understand and maintain.


![[Bildschirm­foto 2023-01-28 um 18.50.42.png]]