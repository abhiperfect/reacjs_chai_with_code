# reacjs_chai_with_code

1. [React JS Roadmap](#react-js-roadmap)
2. [Understanding the React Flow and Structure](#understanding-the-react-flow-and-structure)
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
----

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

## Understanding the React Flow and Structure

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
