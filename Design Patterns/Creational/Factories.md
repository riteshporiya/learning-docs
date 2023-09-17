# Factory Pattern

#### Summary:
The Factory pattern defines an interface for creating an object but allows subclasses to alter the type of objects that will be created.

#### Example:
Suppose we have a word processing application that can create different types of documents, such as resumes and reports.

```js
class Document {
    constructor() {
        this.content = '';
    }
}

class Resume extends Document {
    // Resume-specific content and formatting
}

class Report extends Document {
    // Report-specific content and formatting
}

class DocumentFactory {
    createDocument(type) {
        switch (type) {
            case 'resume':
                return new Resume();
            case 'report':
                return new Report();
            default:
                throw new Error('Invalid document type');
        }
    }
}

// Usage
const factory = new DocumentFactory();
const resume = factory.createDocument('resume');
const report = factory.createDocument('report');
```
In this example, the `DocumentFactory` class provides a method `createDocument` which takes a type as an argument and returns an instance of the corresponding document type (resume or report). This allows for flexibility in creating different types of documents.
