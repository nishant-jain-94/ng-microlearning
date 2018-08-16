# Angular - Level 1

**Objective:** To render a button on the html page and attach a click event with it using **TypeScript**.

## How do we build large scale interactive web pages?

Building interactive webpages requires **JavaScript** but how do we build **Large Scale JavaScript Applications?**. **TypeScript** is the one of the way to build large scale frontend applications.

TypeScript is a superset of JavaScript which primarily provides optional static typing, classes and interfaces. One of the big benefits is to enable IDEs to provide a richer environment for spotting common errors as you type the code.

For a large JavaScript project, adopting TypeScript might result in more robust software, while still being deployable where a regular JavaScript application would run.

## Using TypeScript to build a Basic Interactive Web Page. 
1. **Greeter.ts** contains Greeter class
    ```typescript
    // Create a Greeter Class
    class Greeter {
      greeting: string;
      
      constructor(message: string) {
        this.greeting = message;
      }
      
      greet() {
        return "Hello " + this.greeting;
      }
    }

    let greeter = new Greeter("World");

    // Create a button element 
    let button = document.createElement('button');
    button.textContent = "Say Hello";

    // On Button Click Event show the alert dialog
    button.onclick = function() {
      alert(greeter.greet());
    }

    // Append the button to the document
    document.body.appendChild(button);
    ```
2. In `index.html`
    ```html
    <body>
      <script src="Greeter.js"></script>
    </body>
    ```
3. In `package.json`. Add build and start script. The build script transpiles your `Greeter.ts` to `Greeter.js`
    ```json
    "scripts": {
      "build": "tsc Greeter.ts",
      "start": "npm build && static -p 8090 ."
    }
    ```
    So when you run `npm run build`, it would generate `Greeter.js` and when you run `npm start` it would start your static server and   

## Instructions to start the application
```
# To build the application
npm run build

# To run the application
npm start
```

## Issues
Issues can be raised here at https://github.com/nishant-jain-94/ng-microlearning/issues