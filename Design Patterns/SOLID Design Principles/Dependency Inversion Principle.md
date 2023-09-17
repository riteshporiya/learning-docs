#  Dependency Inversion Principle (DIP)

The DIP suggests that high-level modules should not depend on low-level modules. Both should depend on abstractions, and abstractions should not depend on details.

## Bad Example - Violating DIP

```javascript
class LightBulb {
    turnOn() {
        // Turn on the light bulb
    }
}

class Switch {
    constructor(bulb) {
        this.bulb = bulb;
    }

    toggle() {
        // Toggle the light bulb
    }
}
```
In this example, the `Switch` class depends on the concrete `LightBulb` class, violating DIP.

##Good Example - Following DIP:

```javascript
class Switchable {
    toggle() {
        // Toggle the switchable device
    }
}

class LightBulb extends Switchable {
    turnOn() {
        // Turn on the light bulb
    }
}

class Fan extends Switchable {
    turnOn() {
        // Turn on the fan
    }
}
```
In this improved example, we introduce an abstraction, `Switchable`, which both `LightBulb` and `Fan` inherit from. The `Switch` class now depends on the abstraction rather than concrete implementations, adhering to DIP..
