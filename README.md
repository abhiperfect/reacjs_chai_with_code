# reacjs_chai_with_code
0. [DOM](#dom-document-object-model-manipulation)
1. [React JS Roadmap](#react-js-roadmap)
2. [Create react projects](#create-react-projects)
   - [React + React-DOM vs. React + React-Native](#react--react-dom-vs-react--react-native)
   - [npm and npx](#npm-and-npx)
   - [Creating a React Project](#creating-a-react-project)
     - [Using `create-react-app`](#using-create-react-app)
     - [Using `vite`](#using-vite)
   - [Understanding `package.json`](#understanding-packagejson)
     - [Project Information](#project-information)
     - [Dependencies](#dependencies)
     - [Scripts](#scripts)
     - [ESLint Configuration](#eslint-configuration)
     - [Supporting Browsers (Browserslist)](#supporting-browsers-browserslist)
3. [Understand the react flow and structure](#understand-the-react-flow-and-structure)
----



## DOM (Document Object Model) Manipulation
```markdown

### Introduction

The DOM (Document Object Model) is a programming interface for web documents. It represents the structure of a document as a tree of objects, making it possible for programs to interact with the document's content, structure, and style.

### Key Points

1. **Tree Structure**: The DOM represents an HTML or XML document as a tree structure where each node is an object representing part of the document. These nodes can be elements, attributes, text, or other types of objects.

2. **Access and Manipulation**: Through the DOM, programs can access and modify the content, structure, and styles of documents. This is done using a variety of methods and properties provided by the DOM API. For example, you can change the text of an element, add or remove elements, or alter attributes.

3. **Event Handling**: The DOM allows you to listen for and respond to user interactions such as clicks, input, and other events. This is crucial for creating interactive web applications.

4. **Languages**: While the DOM can be used with various programming languages, it is most commonly used with JavaScript in the context of web browsers.

5. **Dynamic Updates**: The DOM provides the foundation for dynamic content updates in web pages, enabling rich user experiences without needing to reload the entire page.

### Example

Here is a simple example of how the DOM can be used with JavaScript to change the content of an HTML element:

```html
<!DOCTYPE html>
<html>
<head>
  <title>DOM Example</title>
</head>
<body>
  <p id="example">This is a paragraph.</p>
  <button onclick="changeContent()">Change Content</button>

  <script>
    function changeContent() {
      document.getElementById("example").innerText = "The content has been changed!";
    }
  </script>
</body>
</html>
```

In this example, when the button is clicked, the `changeContent` function is executed, which changes the text of the paragraph with the id "example". This demonstrates a simple DOM manipulation.

## DOM Manipulation Methods

### Accessing Elements

1. **`getElementById`**
   ```javascript
   document.getElementById("id");
   ```
2. **`getElementsByClassName`**
   ```javascript
   document.getElementsByClassName("class");
   ```
3. **`getElementsByTagName`**
   ```javascript
   document.getElementsByTagName("tag");
   ```
4. **`querySelector`**
   ```javascript
   document.querySelector("selector");
   ```
5. **`querySelectorAll`**
   ```javascript
   document.querySelectorAll("selector");
   ```

### Creating Elements

1. **`createElement`**
   ```javascript
   document.createElement("tag");
   ```

### Appending and Removing Elements

1. **`appendChild`**
   ```javascript
   parentNode.appendChild(newNode);
   ```
2. **`insertBefore`**
   ```javascript
   parentNode.insertBefore(newNode, referenceNode);
   ```
3. **`removeChild`**
   ```javascript
   parentNode.removeChild(childNode);
   ```
4. **`replaceChild`**
   ```javascript
   parentNode.replaceChild(newNode, oldNode);
   ```

### Modifying Element Content

1. **`innerHTML`**
   ```javascript
   element.innerHTML = "new content";
   ```
2. **`innerText` / `textContent`**
   ```javascript
   element.innerText = "new text";
   element.textContent = "new text";
   ```

### Modifying Attributes

1. **`getAttribute`**
   ```javascript
   element.getAttribute("attribute");
   ```
2. **`setAttribute`**
   ```javascript
   element.setAttribute("attribute", "value");
   ```
3. **`removeAttribute`**
   ```javascript
   element.removeAttribute("attribute");
   ```

### Modifying Classes

1. **`classList.add`**
   ```javascript
   element.classList.add("class");
   ```
2. **`classList.remove`**
   ```javascript
   element.classList.remove("class");
   ```
3. **`classList.toggle`**
   ```javascript
   element.classList.toggle("class");
   ```
4. **`classList.contains`**
   ```javascript
   element.classList.contains("class");
   ```

### Modifying Styles

1. **`style.property`**
   ```javascript
   element.style.property = "value";
   ```

### Event Handling

1. **`addEventListener`**
   ```javascript
   element.addEventListener("event", function);
   ```
2. **`removeEventListener`**
   ```javascript
   element.removeEventListener("event", function);
   ```

### Traversing the DOM

1. **`parentNode`**
   ```javascript
   element.parentNode;
   ```
2. **`childNodes`**
   ```javascript
   element.childNodes;
   ```
3. **`firstChild`**
   ```javascript
   element.firstChild;
   ```
4. **`lastChild`**
   ```javascript
   element.lastChild;
   ```
5. **`nextSibling`**
   ```javascript
   element.nextSibling;
   ```
6. **`previousSibling`**
   ```javascript
   element.previousSibling;
   ```
7. **`children`**
   ```javascript
   element.children;
   ```
8. **`firstElementChild`**
   ```javascript
   element.firstElementChild;
   ```
9. **`lastElementChild`**
   ```javascript
   element.lastElementChild;
   ```
10. **`nextElementSibling`**
   ```javascript
   element.nextElementSibling;
   ```
11. **`previousElementSibling`**
   ```javascript
   element.previousElementSibling;
   ```

### Working with Forms

1. **`form.elements`**
   ```javascript
   form.elements;
   ```
2. **`form.submit`**
   ```javascript
   form.submit();
   ```
3. **`form.reset`**
   ```javascript
   form.reset();
   ```

### Node Manipulation

1. **`cloneNode`**
   ```javascript
   node.cloneNode(true/false); // true for deep clone
   ```
2. **`normalize`**
   ```javascript
   element.normalize();
   ```

These methods cover a wide range of operations you can perform on the DOM to dynamically create, modify, and interact with the web document.

---

## React JS Roadmap

### Why Learn React?

- **Trending and Widely Used**: React is a popular choice for building user interfaces.
- **Managing Complex Frontends**: While UI can be built with jQuery and CSS libraries, React simplifies the management and construction of complex frontends.
    - **Complex Frontends**: React efficiently handles state changes, ensuring that updates in one part of the application reflect seamlessly across the entire UI.

### When Should I Learn React?

- **Project Phases**: Most projects don't need React in the initial phase.
- **Simple Tasks**: Simple tasks like fetching data from an API and displaying it in a card do not require React.

### Why Was React Created?

- **Phantom Message Problem on Facebook**
- **State Management**: JavaScript manages the state (like variables), while the Document Object Model (DOM) manages the UI.
  

  <img src="image.png" width="100px">

  - **State and UI Synchronization**: The state, such as the message count, is stored in a variable and displayed in the UI. Before React, state and DOM were not synchronized, causing state changes to not reflect directly in the UI without a refresh.

- **Early Adopters**: Khan Academy and Unsplash were among the first to use React in their projects.

### React Learning Process

1. **Go In-Depth**:
   - Learn Babel
   - Learn Fiber
   - Learn Virtual DOM
   - Learn Diffing Algorithm
   - Learn Hydration

2. **By Making Projects**:
   - Apply the in-depth topics by building projects.

### React is a Library!

- [Framework vs. Library](https://www.programmingcube.com/framework-vs-library/)

- **Frameworks**: Follow certain rules, e.g., Django.
- **Libraries**: Offer freedom and flexibility, e.g., React.

### Topics to Learn

- **Core Concepts**: State and UI Manipulation, JSX (HTML embedded in JavaScript).
- **Component Reusability**: Use props to reuse components like cards, footers, headers, etc., in different places.
- **Propagating Changes**: Learn about hooks for managing state and effects.

### Additional Add-ons for React

*React enables single-page applications without reloading. To manage URLs, use `react-router`.*

- **Router**: React does not have a built-in router.
  - Install `react-router-dom` to use routing in React projects.
- **State Management**: React does not include built-in state management.
    - Use libraries like `Redux`, `Redux Toolkit` (an abstraction of Redux), Zustand, or `Context API` (all JavaScript libraries).
- **Class-Based Components**: Used in legacy code; modern React uses functional components.
- **BAAS Apps (Backend as a Service)**:
    - Utilize services like Firebase or Supabase to avoid writing backend from scratch.
    - Create social media clones, e-commerce apps, etc., using BAAS.

### After Learning React

- **Limitations**: React does not have built-in SEO capabilities, JavaScript rendering on the server, or default routing.
- **Frameworks**:
  - **Next.js**: Integrates backend and frontend within a single page.
  - **Gatsby**
  - **Remix**
----

## Create react projects

### React + React-DOM vs. React + React-Native

- **React + React-DOM**: Used for building web applications.
- **React + React-Native**: Used for building mobile applications.

### npm and npx

- **npm (Node Package Manager)**: Used for managing packages.
- **npx (Node Package Executer)**: Used for running Node packages without globally installing them.

### Creating a React Project

1. **Using `create-react-app`**

    ```sh
    npx create-react-app project01
    ```
    
    - `create-react-app` is a utility for creating new React projects.
    - **Commands**:
        - `npm run start`: Runs the project in development mode.
        - `npm run build`: Builds the project for production, creating an additional `build` folder.
    - **Note**: 
        - `create-react-app` is a bulky utility and not the fastest way to create a React app.
        - It is not recommended for larger projects.

   
    <img src="image-2.png" width="400px">
   
2. **Using `vite`**

    ```sh
    npm create vite@latest
    ```
    
    - `vite` is a faster bundler for creating React apps.
    - **Commands**:
        - `npm run dev`: Starts the project in development mode.

### Understanding `package.json`

```json
{
  "name": "01basicreact",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.17.0",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
```

- **Project Information**:
    ```json
    "name": "01basicreact",  // Project name
    "version": "0.1.0",      // Project version
    ```

- **Dependencies**:
    - **Testing Libraries**:
        ```json
        "@testing-library/jest-dom": "^5.17.0",
        "@testing-library/react": "^13.4.0",
        "@testing-library/user-event": "^13.5.0",
        ```
    - **Web Vitals**:
        ```json
        "web-vitals": "^2.1.4"
        ```
        - Used to track the performance of your application.

- **Scripts**:
    ```json
    "scripts": {
      "start": "react-scripts start",
      "build": "react-scripts build",
      "test": "react-scripts test",
      "eject": "react-scripts eject"
    }
    ```
    - `start`: Runs the project in a development environment.
    - `build`: Builds the project for production.
    - `test`: Runs test cases.
    - `eject`: Allows you to customize the project configuration.

- **ESLint Configuration**:
    ```json
    "eslintConfig": {
      "extends": [
        "react-app",
        "react-app/jest"
      ]
    }
    ```
    - ESLint helps maintain coding standards and minimize errors. This is particularly important for JavaScript, which is prone to developer errors due to its dynamic and loosely-typed nature.

### Supporting Browsers (Browserslist)

```json
"browserslist": {
  "production": [
    ">0.2%",
    "not dead",
    "not op_mini all"
  ],
  "development": [
    "last 1 chrome version",
    "last 1 firefox version",
    "last 1 safari version"
  ]
}
```
- Specifies the browsers supported by your project in both production and development environments.

----
