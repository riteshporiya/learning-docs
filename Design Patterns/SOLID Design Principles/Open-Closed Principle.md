# Open/Closed Principle (OCP)

The OCP suggests that software entities should be open for extension but closed for modification. In JavaScript, this often involves using inheritance and polymorphism.

## Bad Example - Violating OCP

```javascript
class Rectangle {
    constructor(width, height) {
        this.width = width;
        this.height = height;
    }
}

class AreaCalculator {
    calculateArea(rectangle) {
        return rectangle.width * rectangle.height;
    }
}

// Later, you need to calculate the area of a circle
class Circle {
    constructor(radius) {
        this.radius = radius;
    }
}

// You must modify the AreaCalculator class to add circle support
class AreaCalculator {
    calculateArea(shape) {
        if (shape instanceof Rectangle) {
            return shape.width * shape.height;
        } else if (shape instanceof Circle) {
            return Math.PI * shape.radius * shape.radius;
        }
    }
}
```
This code violates OCP because when we introduce a new shape (like `Circle`), we must modify the `AreaCalculator` class.

##Good Example - Following OCP:

```javascript
class Shape {
    area() {
        // Calculate the area for each shape
    }
}

class Rectangle extends Shape {
    constructor(width, height) {
        super();
        this.width = width;
        this.height = height;
    }

    area() {
        return this.width * this.height;
    }
}

class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }

    area() {
        return Math.PI * this.radius * this.radius;
    }
}
```
In this improved example, we use a common base class `Shape` with a method `area()`. Each specific shape (`Rectangle`, `Circle`, etc.) extends `Shape` and implements its own `area()` method. This way, we can add new shapes without modifying existing code, adhering to OCP.
