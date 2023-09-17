# Prototype Pattern

#### Summary:
The Prototype pattern creates new objects by copying an existing object, known as the prototype, instead of creating objects from scratch.

#### Example:
Imagine a drawing application where users can create shapes like circles and squares. We can use the Prototype pattern to clone existing shapes.

```js
class Shape {
    constructor() {
        this.color = '';
    }

    clone() {
        return Object.assign({}, this);
    }
}

class Circle extends Shape {
    // Circle-specific properties and methods
}

class Square extends Shape {
    // Square-specific properties and methods
}

// Usage
const circlePrototype = new Circle();
const newCircle = circlePrototype.clone();
newCircle.color = 'red'; // Modify the cloned circle's color
```
In this example, `Shape` serves as the prototype. The `clone()` method creates a copy of the existing shape. This allows us to easily create new shapes by cloning the prototype and making any necessary modifications.
