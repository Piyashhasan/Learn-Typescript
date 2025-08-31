<!-- Banner (replace with your image if available) -->
<p align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4D12AQFptCINerHuiQ/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1691780594440?e=2147483647&v=beta&t=Mez7l5p7d27DJpWf3yIoXMQfGcjyRcc4Ye4F926lgRQ" alt="Banner" width="100%" />
</p>

<h1 align="center">All About TypeScript</h1>

> ✅ **Author**: [Piyash Hasan](https://github.com/piyashhasan)  
> 📝 **Topic**: TypeScript </br>
> 📅 **Published**: 24 August 2025

## Table of Contents

- [Install TypeScript](#install-typescript--)
- [Introduction to TypeScript](#introduction-to-typescript--)
- [All About Types](#all-about-types--)
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

    - **Primitive Types**

      - Number
      - String
      - Boolean
      - Null & Undefine
      - BigInt
      - Symbol

    - **Special Types**

      - Any
      - Unknown
      - Never
      - Void

    - **Union Types**
    - **Intersection Types**
    - **Collection Types**

      - Array

    - **Tuples**
    - **Enums**
    - **Object & Interface**
    - **Class**
    - **Utility Types**

    **Primitive Types:**

    - **Number**

      Represents numeric values. TypeScript supports integers, floats, and hexadecimal numbers.

      ```ts
      let age: number = 25;
      let price: number = 99.99;
      let hexValue: number = 0xff; // hexadecimal
      ```

    - **String**

      Represents text values. Strings can use single quotes, double quotes, or backticks (template literals).

      ```ts
      let firstName: string = "Piyash";
      let lastName: string = "Hasan";
      let greeting: string = `Hello, ${firstName} ${lastName}!`;
      ```

    - **Boolean**

      Represents true or false values.

      ```ts
      let isLoggedIn: boolean = true;
      let hasAccess: boolean = false;
      ```

    - **Null & Undefine**

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

    - **BigInt**

      Represents very large integers beyond the safe integer limit of number. Denoted with n at the end.

      ```ts
      let bigNumber: bigint = 9007199254740991n;
      let anotherBig: bigint = BigInt(12345678901234567890);
      ```

    - **Symbol**

      Represents a unique and immutable value, often used as an object property key.

      ```ts
      let uniqueId: symbol = Symbol("id");
      let anotherId: symbol = Symbol("id");

      console.log(uniqueId === anotherId); // false, each symbol is unique
      ```

    **Special Types:**

    - **any**

      - The any type allows a variable to hold any type of value.
      - It disables type checking, which can be useful for gradual migration from JavaScript but should be used carefully.

      </br>

      ```ts
      let randomValue: any = 10; // assign number
      randomValue = "Hello"; // assign string
      randomValue = true; //assign boolean

      console.log(randomValue); // true
      ```

    - **unknown**

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

    - **never**

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

    - **void**

      - Represents absence of a value
      - Often used as the return type of functions that don’t return anything.

        </br>

      ```ts
      function logMessage(message: string): void {
        console.log(message);
      }

      logMessage("Hello TypeScript!");
      ```

    **Union Types:**

    A Union Type allows a variable to hold more than one type. It is written using the pipe (|) symbol.

    ```ts
    let value: string | number;
    value = "Hello"; // ✅ string
    value = 100; // ✅ number
    ```

    **Why Use Union Types?**

    - Makes variables flexible (can hold multiple types).
    - Reduces duplication (no need to declare multiple variables).
    - Improves type safety compared to any.

    **Basic Union Type Example -**

    ```ts
    let id: number | string;
    id = 123; // ✅ number
    id = "ABC123"; // ✅ string
    ```

    **Union with Primitive Types -**

    ```ts
    let result: number | boolean;
    result = 10; // ✅
    result = true; // ✅
    ```

    **Union with Arrays -**

    ```ts
    let values: (string | number)[] = [1, "two", 3, "four"];
    ```

    **Union with Functions -**

    - A function can accept multiple types for parameters.

      ```ts
      function printId(id: number | string) {
        console.log("ID:", id);
      }

      printId(101); // ✅ number
      printId("ABC123"); // ✅ string
      ```

    **Union with Object Types -**

    ```ts
    type User = { id: number; name: string };
    type Guest = { id: string; guest: true };

    let person: User | Guest;

    person = { id: 1, name: "Piyash" }; // ✅ User
    person = { id: "G-123", guest: true }; // ✅ Guest
    ```

    **Literal Unions -**

    - Restrict a variable to specific values.

      ```ts
      type Direction = "Up" | "Down" | "Left" | "Right";

      let move: Direction;
      move = "Up"; // ✅
      move = "Left"; // ✅
      move = "Forward"; // ❌ Error
      ```

    **Union with Type Aliases -**

    ```ts
    type ID = number | string;

    function printId(id: ID) {
      console.log("ID:", id);
    }
    ```

    **Discriminated Unions -**

    - Great for handling multiple object shapes safely.

      ```ts
      type Square = { kind: "square"; size: number };
      type Circle = { kind: "circle"; radius: number };

      type Shape = Square | Circle;

      function area(shape: Shape) {
        switch (shape.kind) {
          case "square":
            return shape.size * shape.size;
          case "circle":
            return Math.PI * shape.radius ** 2;
        }
      }
      ```

    **Intersection Types:**

    An Intersection Type (&) combines multiple types into one. The resulting type must satisfy all types simultaneously.

    ```ts
    type A = { name: string };
    type B = { age: number };

    type Person = A & B;

    let user: Person = {
      name: "Piyash",
      age: 24,
    };
    ```

    Here, Person must have both name and age.

    **Why Use Intersection Types?**

    - Combine multiple types into one.
    - Enforce multiple contracts at once.
    - Useful in mixin patterns and complex models.

    **Basic Intersection Example -**

    ```ts
    type User = { id: number };
    type Employee = { role: string };

    type Staff = User & Employee;

    let staff: Staff = {
      id: 101,
      role: "Developer",
    };
    ```

    **Intersection with Primitive Types -**

    ```ts
    type A = string & number;
    // ❌ Impossible type, no value can be both string and number
    ```

    **Intersection with Type Aliases -**

    ```ts
    type HasId = { id: number };
    type HasTimestamp = { createdAt: Date };

    type RecordType = HasId & HasTimestamp;

    let record: RecordType = {
      id: 1,
      createdAt: new Date(),
    };
    ```

    **Intersection with Unions -**

    ```ts
    type Admin = { role: "admin"; permissions: string[] };
    type User = { role: "user"; email: string };

    type AdminUser = Admin & User;
    // Must have both role:"admin" and role:"user" → ❌ rarely useful

    //👉 More practical with shared structures:

    type Shape = { color: string };
    type Circle = { radius: number };

    type ColoredCircle = Shape & Circle;

    let cc: ColoredCircle = {
      color: "red",
      radius: 10,
    };
    ```

    **Intersection with Functions -**

    ```ts
    type Add = (a: number, b: number) => number;
    type Log = (msg: string) => void;

    type Combined = Add & Log;
    // Function must satisfy both (rare use case)
    ```

    **Intersection with Object Types -**

    ```ts
    type Contact = { email: string };
    type Profile = { username: string };

    type Account = Contact & Profile;

    let account: Account = {
      email: "test@example.com",
      username: "piyash",
    };
    ```

    **Collection Types:**

    - **Array**

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

      **Accessing and Modifying Array Elements:**

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

      **Array with Multiple Types (Union Types):**

      ```ts
      let mixedArray: (number | string)[] = [1, "Two", 3, "Four"];
      mixedArray.push(5);
      mixedArray.push("Six");
      ```

      **Readonly Arrays:**

      - Prevents modification of array elements.
      - You can only read array.

      </br>

      ```ts
      let readonlyNumbers: readonly number[] = [1, 2, 3];
      // readonlyNumbers.push(4); // ❌ Error
      ```

      **Array Methods (Commonly Used):**

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

      **Array Destructuring:**

      ```ts
      let fruits: string[] = ["Apple", "Banana", "Mango"];
      let [first, second, third] = fruits;

      console.log(first); // "Apple"
      console.log(second); // "Banana"
      ```

      **Spread Operator with Arrays:**

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

    **Enums:**

    Enums (short for enumerations) are a way to define a set of named constants in TypeScript. They make code more readable and maintainable.

    ```ts
    enum Direction {
      Up,
      Down,
      Left,
      Right,
    }

    let move: Direction = Direction.Up;
    console.log(move); // Output: 0
    ```

    Why use Enums?

    - Improves code readability
    - Prevents using hardcoded values
    - Helps in maintaining consistent values

    Enum Types in TypeScript?

    - Numeric Enums (Default)

      - By default, enums are numeric, starting from 0.

      </br>

      ```ts
      enum Status {
        Success, // 0
        Failure, // 1
        Pending, // 2
      }
      console.log(Status.Success); // 0
      console.log(Status[1]);
      ```

    - String Enums

      - You can assign string values instead of numbers.

      </br>

      ```ts
      enum Role {
        Admin = "ADMIN",
        User = "USER",
        Guest = "GUEST",
      }
      console.log(Role.Admin); // ADMIN
      ```

    - Heterogeneous Enums

      - Mix of string and numeric values (not recommended often).

      </br>

      ```ts
      enum Mixed {
        Yes = "YES",
        No = 0,
      }
      console.log(Mixed.Yes); // YES
      ```

    Reverse Mapping in Enums -

    - Works only for numeric enums (not string enums).

      </br>

    ```ts
    enum Colors {
      Red,
      Green,
      Blue,
    }
    console.log(Colors.Red); // 0
    console.log(Colors[0]);
    ```

    Enums vs Objects -

    - Enums are compiled into objects at runtime. But enums provide reverse mapping and better type safety.

    Advanced Enum Usage in Real Projects -

    - API status codes
    - User roles/permissions
    - Configurable app modes

      </br>

    ```ts
    enum HttpStatus {
      OK = 200,
      NotFound = 404,
      InternalError = 500,
    }

    function handleResponse(code: HttpStatus) {
      if (code === HttpStatus.OK) {
        return "Request successful!";
      }
      return "Error occurred!";
    }
    ```

    **Objects:**

    In TypeScript, an object is a collection of key-value pairs where keys are strings (or symbols) and values can be of any type.

    ```ts
    // Example: Simple object
    let person = {
      name: "Piyash",
      age: 24,
      isDeveloper: true,
    };
    ```

    **Explicit Object Type -**

    You can define an object type using type annotations.

    ```ts
    let user: { name: string; age: number; isActive: boolean } = {
      name: "Hasan",
      age: 25,
      isActive: true,
    };
    ```

    **Optional Properties (?) -**

    Sometimes, not all properties are required.

    ```ts
    type User = {
      name: string;
      age?: number; // optional
    };

    let u1: User = { name: "Piyash" }; // ✅ allowed
    let u2: User = { name: "Hasan", age: 24 }; // ✅ allowed
    ```

    **Readonly Properties -**

    Use readonly to make properties immutable.

    ```ts
    type Car = {
      readonly brand: string;
      model: string;
    };

    let myCar: Car = { brand: "Tesla", model: "Model S" };
    myCar.model = "Model X"; // ✅ allowed
    // myCar.brand = "BMW"; // ❌ Error: brand is readonly
    ```

    **Index Signatures (Dynamic Keys) -**

    When you don’t know all property names in advance.

    ```ts
    type StringDictionary = {
      [key: string]: string;
    };

    let colors: StringDictionary = {
      red: "FF0000",
      green: "00FF00",
    };
    colors.blue = "0000FF"; // ✅
    ```

    **Nested Objects -**

    Objects inside objects.

    ```ts
    type Employee = {
      id: number;
      details: {
        name: string;
        position: string;
      };
    };

    let emp: Employee = {
      id: 1,
      details: {
        name: "Piyash",
        position: "Frontend Developer",
      },
    };
    ```

    **Objects with Functions (Methods) -**

    ```ts
    type Product = {
      name: string;
      price: number;
      getDiscountedPrice(discount: number): number;
    };

    let laptop: Product = {
      name: "MacBook",
      price: 2000,
      getDiscountedPrice(discount) {
        return this.price - discount;
      },
    };

    console.log(laptop.getDiscountedPrice(200)); // 1800
    ```

    **Class:**

    A class is a blueprint for creating objects.

    It can contain:

    - Properties → variables inside a class
    - Methods → functions inside a class

    Basic Class Example -

    ```ts
    class Person {
      name: string;
      age: number;

      // Constructor is called when creating a new object
      constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
      }

      // Method
      greet(): void {
        console.log(
          `Hello, my name is ${this.name} and I am ${this.age} years old.`
        );
      }
    }

    // Creating an object
    let p1 = new Person("Piyash", 24);
    p1.greet(); // Output: Hello, my name is Piyash and I am 24 years old.
    ```

    > **Note:** We will explore Classes in depth, along with Object-Oriented Programming (OOP) concepts in TypeScript, in the dedicated Classes & OOP section

    </br>

    **Utility Types in TypeScript (Built-in):**

    TypeScript provides several built-in utility types that help transform existing types into new ones. These are very useful when working with objects and APIs.

    - Partial<T> :

      Makes all properties optional.

      ```ts
      type User = {
        id: number;
        name: string;
        email: string;
      };

      type PartialUser = Partial<User>;

      let u1: PartialUser = { name: "Piyash" }; // ✅ only 'name' provided
      let u2: PartialUser = {}; // ✅ even empty object is allowed
      ```

      > **Note:** 👉 Use when updating part of an object (e.g., PATCH request in APIs).

    - Readonly<T>

      Makes all properties immutable (cannot be changed).

      ```ts
      type Person = {
        id: number;
        name: string;
        age: number;
        email: string;
      };

      type PersonName = Pick<Person, "id" | "name">;

      let p: PersonName = { id: 1, name: "Hasan" }; // ✅ only 'id' & 'name'
      ```

      > **Note:** 👉 Use when you want to prevent accidental changes.

    - Pick<T, K>

      Creates a new type by choosing specific properties from another type.

      ```ts
      type Person = {
        id: number;
        name: string;
        age: number;
        email: string;
      };

      type PersonName = Pick<Person, "id" | "name">;

      let p: PersonName = { id: 1, name: "Hasan" }; // ✅ only 'id' & 'name'
      ```

      > **Note:** 👉 Useful when you need only some properties.

    - Omit<T, K>

      The opposite of Pick → removes specific properties.

      ```ts
      type Employee = {
        id: number;
        name: string;
        department: string;
      };

      type WithoutDept = Omit<Employee, "department">;

      let e: WithoutDept = { id: 101, name: "Piyash" }; // ✅ no 'department'
      ```

      > **Note:** 👉 Useful when you need all except certain properties.

    - Record<K, T>

      Creates an object type with keys of type K and values of type T.

      ```ts
      type Roles = "admin" | "user" | "guest";

      type RolePermissions = Record<Roles, string[]>;

      let permissions: RolePermissions = {
        admin: ["create", "read", "update", "delete"],
        user: ["read", "update"],
        guest: ["read"],
      };
      ```

      > **Note:** 👉 Useful when creating maps / dictionaries.

    - Required<T>

      Makes all optional properties required.

      ```ts
      type Profile = {
        username?: string;
        email?: string;
      };

      type FullProfile = Required<Profile>;

      let p: FullProfile = {
        username: "piyash",
        email: "test@mail.com",
      }; // ✅ now both required
      ```

      > **Note:** 👉 Useful when you want to enforce all fields must be filled.

6.  **Type Assertion Vs Type Casting -**

    - Type Assertion

      Type Assertion is a way in TypeScript to tell the compiler:

      > **Note:** 👉 “Trust me, I know the actual type of this value better than you do.”

      It does not change the runtime value — it only affects compile-time checking.

      ```ts
      let someValue: unknown = "Hello TypeScript";

      // Assert as a string
      let strLength: number = (someValue as string).length;

      console.log(strLength); // 16
      ```

    - Explanation:

      - someValue is declared as unknown.
      - The compiler doesn’t know it’s a string.
      - We assert that someValue is a string with (someValue as string).
      - Now, TypeScript allows us to use .length.

      </br>

      > **Note:** Type assertion doesn’t convert data — at runtime it’s still the same "Hello TypeScript".

    - Type Casting

      Type Casting generally means converting one type of data to another at runtime.

      👉 This is different from TypeScript’s type system, because casting really changes the data.

      ```ts
      let numStr: string = "123";

      // Convert string to number (type casting)
      let num: number = Number(numStr);

      console.log(num); // 123
      console.log(typeof num); // "number"
      ```

      - Explanation:

        - Here, "123" (a string) is cast/converted into 123 (a number).

        - This is runtime conversion, not just a compile-time hint.

      **Are Type Assertion & Type Casting the Same?**

      > **Note:** ❌ No, they are not the same.

      | Feature            | Type Assertion (TS only)                               | Type Casting (JS/Runtime)                     |
      | ------------------ | ------------------------------------------------------ | --------------------------------------------- |
      | **Definition**     | Tells compiler to treat a value as a specific type     | Converts data from one type to another        |
      | **Runtime Effect** | No effect (compile-time only)                          | Actually changes the data                     |
      | **Example**        | `value as string `                                     | `Number("123")       `                        |
      | **Use case**       | When compiler is unsure, but you know the correct type | When you need to change value type at runtime |

      **Quick Combined Example-**

      ```ts
      let value: unknown = "42";

      // ✅ Type Assertion
      let strValue: string = value as string;
      console.log(strValue.length); // Works, compiler trusts us

      // ✅ Type Casting
      let numValue: number = Number(strValue);
      console.log(numValue + 10); // 52
      ```

    - Non-Null Assertion Operator (!) in TypeScript

      The non-null assertion operator (!) is used in TypeScript to tell the compiler:

      > **Note:** “I’m sure this value is not null or undefined — trust me.”

      It doesn’t change runtime behavior; it only affects compile-time type checking.

      ```ts
      let username: string | null = null;

      // Compiler error ❌: Object is possibly 'null'.
      console.log(username.length);
      ```

      Here, since username could be null, TypeScript does not allow direct access to .length.

      🔹 Example With (!)

      ```ts
      let username: string | null = "Piyash";

      // Using non-null assertion
      console.log(username!.length); // ✅ 6
      ```

      Explanation -

      - username has the type string | null.
      - By writing username!, we tell the compiler: “Don’t worry, username is not null here.”
      - So, TypeScript allows .length.

      </br>

      > **Note:** ! does not remove null at runtime. If the value is actually null or undefined, you’ll get a runtime error.

7.  **Type Narrowing-**

    In TypeScript, Type Narrowing means refining a variable’s type based on certain checks. If a variable has a union type, narrowing helps the compiler understand what the type really is at a specific point in code.

    ```ts
    function printValue(value: string | number) {
      if (typeof value === "string") {
        // TypeScript now knows 'value' is a string
        console.log("Uppercased:", value.toUpperCase());
      } else {
        // Here 'value' is narrowed to number
        console.log("Doubled:", value * 2);
      }
    }

    printValue("hello"); // Uppercased: HELLO
    printValue(10); // Doubled: 20
    ```

    - `typeof` Type Guards

      The typeof operator is used to check the type of a primitive value at runtime.
      It’s useful for narrowing types like `string | number | boolean.`

      ```ts
      function printValue(value: string | number) {
        if (typeof value === "string") {
          console.log("String in uppercase:", value.toUpperCase());
        } else {
          // Here TypeScript knows value must be a number
          console.log("Number doubled:", value * 2);
        }
      }

      printValue("hello"); // String in uppercase: HELLO
      printValue(10); // Number doubled: 20
      ```

      > **Note:** 👉 Here, `typeof` narrows the type inside each branch.

    - `instanceof` Instance Of

      The `instanceof` operator checks if an object is an instance of a particular class or constructor function.
      It’s useful for narrowing object types.

      ```ts
      class Dog {
        bark() {
          console.log("Woof!");
        }
      }

      class Cat {
        meow() {
          console.log("Meow!");
        }
      }

      function makeSound(animal: Dog | Cat) {
        if (animal instanceof Dog) {
          animal.bark(); // ✅ Compiler knows animal is Dog here
        } else {
          animal.meow(); // ✅ Otherwise, it's Cat
        }
      }

      makeSound(new Dog()); // Woof!
      makeSound(new Cat()); // Meow!
      ```

      > **Note:** 👉 `instanceof` narrows down which class the object belongs to.

    - Custom Type Predicates

      Sometimes typeof and instanceof aren’t enough, especially for interfaces or complex objects.
      In those cases, we can define our own type guard functions with a type predicate (parameterName is Type).

      ```ts
      type Car = { drive: () => void };
      type Bike = { ride: () => void };

      function isCar(vehicle: Car | Bike): vehicle is Car {
        return (vehicle as Car).drive !== undefined;
      }

      function useVehicle(vehicle: Car | Bike) {
        if (isCar(vehicle)) {
          vehicle.drive(); // ✅ Compiler knows vehicle is Car here
        } else {
          vehicle.ride(); // ✅ Otherwise, it's Bike
        }
      }

      let myCar: Car = { drive: () => console.log("Driving car...") };
      let myBike: Bike = { ride: () => console.log("Riding bike...") };

      useVehicle(myCar); // Driving car...
      useVehicle(myBike); // Riding bike...
      ```

      **Summary Table**

      | Technique                 | Works With                | Example Use Case                                  |
      | ------------------------- | ------------------------- | ------------------------------------------------- |
      | `typeof`                  | Primitive types           | Check if a value is `string, number, boolean` etc |
      | `instanceof`              | Classes / Constructors    | Distinguish between different class instances     |
      | **Custom Type Predicate** | Interfaces / Custom types | Check if an object matches a specific shape       |

8.  **Indexed Access & Keyof-**

    - `keyof` Operator

      The keyof operator is used to get the keys of a type as a union of string literals.

      ```ts
      type Person = {
        id: number;
        name: string;
        email: string;
      };

      type PersonKeys = keyof Person;
      // Equivalent to: "id" | "name" | "email"

      let key: PersonKeys;

      key = "id"; // ✅
      key = "name"; // ✅
      key = "email"; // ✅
      // key = "age"; ❌ Error: not a key of Person
      ```

      > **Note:** 👉 keyof is useful when you want to restrict values to the keys of an object type.

      **Example: With Index Signatures**

      ```ts
      type Dictionary = {
        [key: string]: number;
      };

      type DictKeys = keyof Dictionary;
      // string | number (because object keys can also be numbers)
      ```

      - Indexed Access Types `(T["key"])`

        This lets you access the type of a property from another type.

        ```ts
        type Person = {
          id: number;
          name: string;
          email: string;
        };

        type NameType = Person["name"]; // string
        type IdType = Person["id"]; // number
        type EmailType = Person["email"]; // string
        ```

        > **Note:** 👉 This is like looking up a property’s type.

        **Example: Multiple Keys**

        You can extract multiple property types at once.

        ```ts
        type Person = {
          id: number;
          name: string;
          email: string;
        };

        type IdAndName = Person["id" | "name"];
        // number | string
        ```

        **Example: Using keyof with Indexed Access**

        ```ts
        type Person = {
          id: number;
          name: string;
          email: string;
        };

        type AllValues = Person[keyof Person];
        // number | string
        ```

        > **Note:** 👉 This gives you a union of all property types.

        **Example: Generic Function with keyof and Indexed Access**

        ```ts
        type Person = {
          id: number;
          name: string;
          email: string;
        };

        function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
          return obj[key];
        }

        let user: Person = { id: 1, name: "Piyash", email: "test@mail.com" };

        let nameValue = getValue(user, "name"); // string
        let idValue = getValue(user, "id"); // number
        ```

        - `K extends keyof T` ensures the key must exist.
        - `T[K]` gives us the type of that property.

      **Summary**

      - `keyof` → Extracts all keys of a type as a union.

        ```ts
        type Keys = keyof Person; // "id" | "name" | "email"
        ```

        - Indexed Access (`T["key"]`) → Extracts the type of a specific property.

          ```ts
          type NameType = Person["name"]; // string
          ```

        - Combine both for flexible, type-safe utilities.

          ```ts
          type Values = Person[keyof Person]; // union of all property types
          ```

      > **Note:** 👉 This pair (`keyof` + `T["key"]`) is the foundation for advanced TypeScript utilities (like Pick, Omit, Record).
