#  Interface Segregation Principle (ISP)

The ISP suggests that clients should not be forced to depend on interfaces they do not use. In JavaScript, we can implement this principle using classes and methods.

## Bad Example - Violating ISP

```javascript
class Worker {
    work() {
        // Perform some work
    }

    eat() {
        // Eat lunch
    }
}
```
In this example, the `Worker` class forces clients to depend on both the `work()` and `eat()` methods, even if they don't need both.

##Good Example - Following ISP:

```javascript
class Worker {
    work() {
        // Perform some work
    }
}

class Eater {
    eat() {
        // Eat lunch
    }
}
```
In this improved example, we have split the responsibilities into separate classes (`Worker` and `Eater`). Clients can now depend on the class that provides the functionality they need, adhering to ISP.
