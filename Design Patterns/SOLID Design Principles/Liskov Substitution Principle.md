# Liskov Substitution Principle (LSP)

The LSP states that objects of derived classes should be able to replace objects of the base class without affecting program correctness.

## Bad Example - Violating LSP

```javascript
class Bird {
    fly() {
        // Bird-specific flying behavior
    }
}

class Ostrich extends Bird {
    fly() {
        // Ostriches cannot fly, but this method is inherited
    }
}
```
In this example, the `Ostrich` class violates LSP because it inherits the `fly()` method from `Bird`, but ostriches cannot fly.

##Good Example - Following LSP:

```javascript
class Bird {
    fly() {
        // Bird-specific flying behavior
    }
}

class Ostrich {
    // Ostrich-specific behavior, no fly() method
}
```
In this improved example, we have a separate `Ostrich` class without the `fly()` method. This adheres to LSP because you can use an `Ostrich` object wherever you use a `Bird` object without unexpected behavior.
