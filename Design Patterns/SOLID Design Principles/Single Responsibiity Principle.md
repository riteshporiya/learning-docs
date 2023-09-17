# Single Responsibility Principle (SRP)

The SRP states that a class or module should have only one reason to change. It should have a single, well-defined responsibility.

## Bad Example - Violating SRP

```javascript
class User {
  constructor(name) {
    this.name = name;
  }
  
  saveToDatabase() {
    // Save user data to the database
  }
  
  sendEmail() {
    // Send an email to the user
  }
}
```
In this example, the `User` class has two responsibilities: saving data to the database and sending emails. This violates SRP.

##Good Example - Following SRP:

```javascript
class User {
  constructor(name) {
    this.name = name;
  }
}

class UserRepository {
  save(user) {
    // Save user data to the database
  }
}

class EmailService {
  sendEmail(user) {
    // Send an email to the user
  }
}
```
In this improved example, we have split the responsibilities into separate classes. `User` is responsible for representing a user, `UserRepository` handles database operations, and `EmailService` deals with sending emails. Each class has a single responsibility, adhering to SRP.
