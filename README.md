<!-- Banner (replace with your image if available) -->
<p align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4D12AQFptCINerHuiQ/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1691780594440?e=2147483647&v=beta&t=Mez7l5p7d27DJpWf3yIoXMQfGcjyRcc4Ye4F926lgRQ" alt="Banner" width="100%" />
</p>

<h1 align="center">All About TypeScript</h1>

> ✅ **Author**: [Piyash Hasan](https://github.com/piyashhasan)  
> 📝 **Topic**: TypeScript </br>
> 📅 **Published**: 24 August 2025

## Table of Contents

- [Install TypeScript](#install-typescript)
- [Introduction to TypeScript](#introduction-to-typescript)
- [All About Types](#all-about-types)
- [Variables](#variables)
- [Conditionals](#conditionals)
- [Loops](#loops)
- [Functions](#functions)
- [Objects & Interfaces](#objects--interfaces)
- [Interfaces vs Type Aliases](#interfaces-vs-type-aliases)
- [Generics](#generics)
- [Classes & OOP in TypeScript](#classes--oop-in-typescript)
- [Modules & Namespaces](#modules--namespaces)
- [Decorators](#decorators)
- [Mixins](#mixins)
- [Error Handling & Strict Mode](#error-handling--strict-mode)

# Install TypeScript -

## Folder Structure

```
my-typescript-project/
├── src/
│   └── index.ts
├── dist/
│   └── index.js (generated)
├── index.html
├── tsconfig.json
└── package.json
```

## Basic Setup (Simple Compilation)

### Prerequisites

1. **Download and Install Node.js**
   - Visit: [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
   - Download and install the latest LTS version

### Setup Steps

1. **Create a Project Folder**

   ```bash
   mkdir my-typescript-project
   cd my-typescript-project
   ```

2. **Install TypeScript**
   Choose one of the following options:

   **Option A: Dev Dependency (Recommended)**

   ```bash
   npm install typescript --save-dev
   ```

   **Option B: Global Installation**

   ```bash
   npm install -g typescript
   ```

3. **Create TypeScript File**

   ```bash
   touch index.ts
   ```

4. **Compile TypeScript to JavaScript**
   ```bash
   npx tsc index.ts
   ```
   This will generate an `index.js` file in your project directory.

---

## Advanced Setup (With Compiler Options)

### Prerequisites

Follow steps 1-3 from the Basic Setup above.

### Configuration Steps

1. **Initialize TypeScript Configuration**

   ```bash
   tsc --init
   ```

   This automatically creates a `tsconfig.json` file in your project root.

2. **Configure tsconfig.json**
   Open `tsconfig.json` and locate the following options:

   **rootDir**: Specifies the root directory of your TypeScript source files
   **outDir**: Specifies the output directory for compiled JavaScript files

   Update these paths:

   ```json
   {
     "compilerOptions": {
       "rootDir": "./src",
       "outDir": "./dist"
     }
   }
   ```

3. **Create Project Structure**

   ```bash
   mkdir src dist
   touch src/index.ts
   ```

4. **Compile TypeScript**

   ```bash
   tsc
   ```

   This will compile all TypeScript files from `src/` to `dist/` directory.

5. **Create HTML File**
   Create `index.html` in your project root:

   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>TypeScript Project</title>
     </head>
     <body>
       <h1 style="text-align: center; color: #007acc">
         Welcome to TypeScript World...!
       </h1>
       <script src="dist/index.js"></script>
     </body>
   </html>
   ```

6. **Enable Watch Mode (Development)**

   **Terminal 1 - TypeScript Compiler Watch Mode:**

   ```bash
   tsc --watch
   ```

   _Watch mode automatically recompiles your TypeScript files whenever you save changes._

   **Terminal 2 - Node.js Watch Mode:**

   ```bash
   node --watch dist/index.js
   ```

   **Watch (--watch) flag Benefits:**

   - Automatically recompiles files when changes are detected
   - Speeds up development workflow
   - Eliminates need to manually run compile commands

7. **Run Your Project**
   Open `index.html` in your browser to see your code running in the browser console.

## Key Concepts

- TypeScript cannot run directly in browsers
- The TypeScript compiler converts `.ts` files to `.js` files
- JavaScript files can run seamlessly in browsers
- This process enables type safety during development while maintaining browser compatibility

---

# Introduction to TypeScript -

1. **What is TypeScript?**

   TypeScript is an open-source programming language developed and maintained by Microsoft. It is a superset of JavaScript, meaning that it builds upon JavaScript by adding optional static typing and other features.

2. **TypeScript vs JavaScript.**

   | Feature                | JavaScript                                                         | TypeScript                                                                                                           |
   | ---------------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
   | **Definition**         | A scripting language used to create dynamic web applications.      | A superset of JavaScript that adds **static typing** and advanced features.                                          |
   | **Typing**             | **Dynamically typed** (types are checked at runtime).              | **Statically typed** (types are checked at compile time).                                                            |
   | **Error Detection**    | Errors are caught only at **runtime**.                             | Errors are caught at **compile time** before running the code.                                                       |
   | **Compilation**        | Interpreted directly by the browser or Node.js.                    | Needs to be **compiled (transpiled)** into JavaScript before execution.                                              |
   | **Learning Curve**     | Easier to start with (no extra setup).                             | Slightly higher learning curve (requires TypeScript compiler & configuration).                                       |
   | **Tooling Support**    | Good support in modern editors (but limited type checking).        | Excellent support with **intellisense, autocompletion, and refactoring** in editors like VS Code.                    |
   | **Features**           | Supports ES6+ features (classes, arrow functions, promises, etc.). | Includes **all JS features** + additional features like **interfaces, enums, generics, decorators, advanced types**. |
   | **Scalability**        | Best for **small to medium** projects.                             | Best for **large-scale, maintainable** applications.                                                                 |
   | **Community Adoption** | Used everywhere (all browsers, Node.js).                           | Increasingly popular in modern web development (used with Angular, React, Node.js, etc.).                            |

   **In simple terms**:

   - Use **JavaScript** if you want quick prototyping, small projects, or are just starting out.
   - Use **TypeScript** if you want **safer, more maintainable, and scalable applications**.

3. **Benefits over JavaScript**

   - Early error detection
   - Better tooling (IntelliSense, autocompletion)
   - Supports OOP (classes, interfaces)
   - Works with existing JavaScript code

4. **TypeScript Feature**

   | Feature Name                        | How it works                                                    |
   | ----------------------------------- | --------------------------------------------------------------- |
   | **1. Generics**                     | Reusable functions and components with types                    |
   | **2. Enums**                        | Create a named set of constants                                 |
   | **3. Static typing**                | Fix variable type at compile time                               |
   | **4. Type inference**               | TypeScript guesses the type automatically                       |
   | **5. Conditional types**            | Choose a type based on a condition                              |
   | **6. Decorators**                   | Add extra behavior to classes or methods                        |
   | **7. Interfaces**                   | Define the structure of an object                               |
   | **8. Mapped Types**                 | Transform existing types into new ones                          |
   | **9. Type Guards**                  | Check the type of a variable at runtime                         |
   | **10. Const assertions**            | Make values readonly or literal types                           |
   | **11. Namespaces**                  | Organize code into logical groups                               |
   | **12. Template literal types**      | Create types using string patterns                              |
   | **13. ES6 features**                | Use modern JS features like let/const, arrow functions, classes |
   | **14. Infer keyword**               | Extract type automatically inside conditional types             |
   | **15. Object oriented programming** | Use classes, inheritance, and encapsulation                     |
   | **16. Optional Chaining**           | Safely access nested properties without errors                  |
   | **17. Supports type definitions**   | Use external `.d.ts` files for libraries                        |
   | **18. Tuples**                      | Fixed-size array with specific types for each element           |
   | **19. Union**                       | Variable can hold more than one type                            |

> **Note:** We will explore and learn each of the above TypeScript features in detail in the upcoming lessons.

---

# All About Types -

1.  **What is Types?**

    In TypeScript, a type is a label that describes the properties and methods that a value possesses. It defines the "shape" of data, allowing the TypeScript compiler to analyze your code for potential errors and bugs before runtime.

    ```ts
    // Here First Name & Last Name type declare

    let firstName: string = "Piyash";
    let lastName: string = "Hasan";
    ```

2.  **How many ways are there to declare a type in TypeScript?**

    In TypeScript, there are mainly two ways to declare types:

    - Explicit
    - Inferred

      Let me explain both clearly with examples:

    **Explicit Type Declaration**:

    You manually specify the type of a variable when you declare it. This is useful for clarity and avoiding mistakes.

    ```ts
    let firstName: string = "Piyash"; // explicitly declared as string
    let lastName: string = "Hasan"; // explicitly declared as string
    let designation: string = "Software Engineer"; // explicitly declared as string
    let isStudent: boolean = false; // explicitly declared as boolean
    ```

    **Inferred Type Declaration**:

    TypeScript can automatically infer the type based on the value you assign to the variable. You don’t need to write the type manually.

    ```ts
    let firstName = "Piyash"; // TypeScript infers this as string
    let lastName = "Hasan"; // TypeScript infers this as string
    let designation = "Software Engineer"; // TypeScript infers this as string
    let isStudent = false; // TypeScript infers this as boolean
    ```

3.  **What is Type Annotation?**

    Type annotations in TypeScript are a syntax feature used to explicitly declare the data type of variables, function parameters, and function return values. They are a core aspect of TypeScript's static typing system, which allows for type checking during development and compilation, rather than at runtime.

    **How Type Annotations Work:**

    Type annotations are added using a colon (:) followed by the desired type. variables.

    ```ts
    let myString: string = "Hello";
    let myNumber: number = 123;
    ```

4.  **What is Type Aliases ?**

    Type Aliases is a way to using that way you can create a custom type name.

    ```ts
    // Syntax -
    type AliasName = TypeDefinition;

    // Example -
    type NameType = string;
    const myName: NameType = "Piyash Hasan";
    ```

    Here, AliasName denotes the custom name assigned to the type, while TypeDefinition delineates the underlying type structure. Type aliases are versatile, accommodating various types, including primitives, object types, union types, and function signatures.

5.  **Basic Type Categories in TypeScript -**

    - Primitive Types
    - Special Types
    - Collection Types
    - Tuples
    - Enums
    - Object Types
    - Union Types
    - Intersection Types
    - Class
    - Utility Types

    **Primitive Types:**

    - Number

      Represents numeric values. TypeScript supports integers, floats, and hexadecimal numbers.

      ```ts
      let age: number = 25;
      let price: number = 99.99;
      let hexValue: number = 0xff; // hexadecimal
      ```

    - String

      Represents text values. Strings can use single quotes, double quotes, or backticks (template literals).

      ```ts
      let firstName: string = "Piyash";
      let lastName: string = "Hasan";
      let greeting: string = `Hello, ${firstName} ${lastName}!`;
      ```

    - Boolean

      Represents true or false values.

      ```ts
      let isLoggedIn: boolean = true;
      let hasAccess: boolean = false;
      ```

    - Null & Undefine

      - null represents an intentional absence of any value.
      - undefined represents a variable that has been declared but not yet assigned a value.

      </br>

      ```ts
      let emptyValue: null = null; // only emptyValue accept null
      let notAssigned: undefined = undefined; // only notAssigned accept undefined

      // Example -
      let userName: string | null = null; // userName accept string & null both value
      userName = "Piyash";
      ```

      > **Note:** By default, in TypeScript without --strictNullChecks, null and undefined can be assigned to any type.

      **Example without --strictNullChecks:**

      ```ts
      let name: string;
      name = "Piyash"; // OK
      name = null; // Also OK (surprisingly!)
      name = undefined; // Also OK
      ```

      This can be risky because you might not expect null or undefined in your variables.

      **What happens with --strictNullChecks?**

      When --strictNullChecks is enabled, null and undefined are NOT automatically allowed in other types. They are only assignable to:

      - any
      - unknown
      - their respective type (null or undefined)
      - a union type that explicitly includes null or undefined

      **Example with --strictNullChecks:**

      ```ts
      let name: string;
      name = "Piyash"; // OK
      name = null; // ❌ Error
      name = undefined; // ❌ Error

      let maybeName: string | null;
      maybeName = "Piyash"; // OK
      maybeName = null; // OK
      ```

      > **Key point:** You must explicitly allow null or undefined using a union type like string | null.

    - BigInt

      Represents very large integers beyond the safe integer limit of number. Denoted with n at the end.

      ```ts
      let bigNumber: bigint = 9007199254740991n;
      let anotherBig: bigint = BigInt(12345678901234567890);
      ```

    - Symbol

      Represents a unique and immutable value, often used as an object property key.

      ```ts
      let uniqueId: symbol = Symbol("id");
      let anotherId: symbol = Symbol("id");

      console.log(uniqueId === anotherId); // false, each symbol is unique
      ```

    **Special Types:**

    - any

      - The any type allows a variable to hold any type of value.
      - It disables type checking, which can be useful for gradual migration from JavaScript but should be used carefully.

      </br>

      ```ts
      let randomValue: any = 10; // assign number
      randomValue = "Hello"; // assign string
      randomValue = true; //assign boolean

      console.log(randomValue); // true
      ```

    - unknown

      - The unknown type is similar to any but safer.
      - You cannot use it directly without type checking or type assertion.

        ```ts
        let userInput: unknown;
        userInput = "Hello World";
        userInput = 42;

        // Type checking needed
        if (typeof userInput === "string") {
          console.log(userInput.toUpperCase()); // OK
        }
        ```

    - never

      - Represents values that never occur.
      - Commonly used for functions that throw errors or infinite loops.

      </br>

      ```ts
      function throwError(message: string): never {
        throw new Error(message);
      }

      function infiniteLoop(): never {
        while (true) {}
      }
      ```

    - void

      - Represents absence of a value
      - Often used as the return type of functions that don’t return anything.

       </br>

      ```ts
      function logMessage(message: string): void {
        console.log(message);
      }

      logMessage("Hello TypeScript!");
      ```

    **Collection Types:**

    - Array

      In TypeScript, an array is a data structure that allows for storing a collection of multiple items under a single variable name, maintaining a specific order, and providing strong type checking.

      You can declare an array using two main syntaxes:

      - Using type[]

        ```ts
        let numbers: number[] = [1, 2, 3, 4, 5];
        let names: string[] = ["Md", "Piyash", "Hasan"];
        ```

      - Using Array<type>

        ```ts
        let scores: Array<number> = [90, 85, 100];
        let fruits: Array<string> = ["Apple", "Banana", "Mango"];
        ```

      Accessing and Modifying Array Elements:

      ```ts
      let colors: string[] = ["Red", "Green", "Blue"];

      // Access
      console.log(colors[0]); // "Red"

      // Modify
      colors[1] = "Yellow";
      console.log(colors); // ["Red", "Yellow", "Blue"]

      // Add elements
      colors.push("Purple"); // add last
      colors.unshift("Pink"); // add first
      console.log(colors); // ["Pink", "Red", "Yellow", "Blue", "Purple"]

      // Remove elements
      colors.pop(); // removes last
      colors.shift(); // removes first
      ```

      Array with Multiple Types (Union Types):

      ```ts
      let mixedArray: (number | string)[] = [1, "Two", 3, "Four"];
      mixedArray.push(5);
      mixedArray.push("Six");
      ```

      Readonly Arrays:

      - Prevents modification of array elements.
      - You can only read array.

      </br>

      ```ts
      let readonlyNumbers: readonly number[] = [1, 2, 3];
      // readonlyNumbers.push(4); // ❌ Error
      ```

      Array Methods (Commonly Used):

      ```ts
      let nums: number[] = [1, 2, 3, 4, 5];

      // forEach
      nums.forEach((num) => console.log(num * 2));

      // map
      let doubled = nums.map((num) => num * 2);
      console.log(doubled); // [2, 4, 6, 8, 10]

      // filter
      let even = nums.filter((num) => num % 2 === 0);
      console.log(even); // [2, 4]

      // find
      let firstEven = nums.find((num) => num % 2 === 0);
      console.log(firstEven); // 2

      // reduce
      let sum = nums.reduce((acc, val) => acc + val, 0);
      console.log(sum); // 15
      ```

      Array Destructuring:

      ```ts
      let fruits: string[] = ["Apple", "Banana", "Mango"];
      let [first, second, third] = fruits;

      console.log(first); // "Apple"
      console.log(second); // "Banana"
      ```

      Spread Operator with Arrays:

      ```ts
      let arr1: number[] = [1, 2, 3];
      let arr2: number[] = [4, 5, 6];

      let combined: number[] = [...arr1, ...arr2];
      console.log(combined); // [1, 2, 3, 4, 5, 6]
      ```

    **Tuples:**

    Tuples in TypeScript are special kinds of arrays where you can define a Fixed Number of Elements with specific types at specific positions.

    - Basic Tuple Declaration

      ```ts
      let person: [string, number] = ["Piyash", 25]; // declare fixed number of array

      console.log(person[0]); // "Piyash"
      console.log(person[1]); // 25
      ```

      - Unlike normal arrays, each position has a specific type.
      - If you swap them, TypeScript will throw an error.

        ```ts
        // ❌ Error: order matters
        let wrongPerson: [string, number] = [25, "Piyash"];
        ```

    - Tuple with More Elements

      ```ts
      let coordinates: [number, number, number] = [10, 20, 30];
      ```

    - Optional Tuple Elements

      - You can make some elements optional using (?).

      ```ts
      let user: [string, number?];

      user = ["Alice"];
      user = ["Bob", 30];
      ```

    - Rest Elements in Tuples

      - Tuples can have rest elements for flexible lengths.

      ```ts
      let names: [string, ...string[]] = ["Piyash", "Hasan", "Khan"];
      console.log(names); // ["Piyash", "Hasan", "Khan"]
      ```

    - Destructuring Tuples

      - You can unpack values directly

      ```ts
      let student: [string, number] = ["Alice", 21];
      let [name, age] = student;

      console.log(name); // "Alice"
      console.log(age); // 21
      ```

    - Readonly Tuples

      - Use readonly to prevent modification
      - You can only read array.

      ```ts
      let point: readonly [number, number] = [10, 20];
      // point[0] = 30; // ❌ Error: Cannot modify readonly tuple
      ```

    - Named Tuples (for clarity in advanced usage)

      - TypeScript supports naming tuple elements (TypeScript 4.0+).

      ```ts
      let employee: [id: number, name: string, isActive: boolean];
      employee = [1, "Piyash", true];
      ```

    - Tuples in Arrays

      - Array of tuples can model structured data:

      ```ts
      let users: [number, string][] = [
        [1, "Alice"],
        [2, "Bob"],
        [3, "Charlie"],
      ];
      ```
