# Builder Pattern

#### Summary: 
  The Builder pattern separates the construction of a complex object from its representation. It allows the same construction process to create different representations.

#### Example:
Consider a scenario where we want to build a meal in a fast-food restaurant. A meal consists of a burger, a drink, and optional sides.

```js
class Burger {
  constructor(type) {
    this.type = type;
  }
}

class Drink {
  constructor(type) {
    this.type = type;
  }
}

class Meal {
  constructor() {
    this.items = [];
  }

  add(item) {
    this.items.push(item);
  }

  showItems() {
    this.items.forEach(item => console.log(item.type));
  }
}

class MealBuilder {
  constructor() {
    this.meal = new Meal();
  }

  addBurger(burger) {
    this.meal.add(burger);
  }

  addDrink(drink) {
    this.meal.add(drink);
  }

  getMeal() {
    return this.meal;
  }
}

// Usage
const builder = new MealBuilder();
builder.addBurger(new Burger('Cheeseburger'));
builder.addDrink(new Drink('Cola'));
const meal = builder.getMeal();
meal.showItems(); // Output: Cheeseburger, Cola
```
In this example, the `MealBuilder` class separates the construction of a `Meal` object from its representation. It allows us to add different items to the meal, such as burgers and drinks, before retrieving the final `Meal` object.
