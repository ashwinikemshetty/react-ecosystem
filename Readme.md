# React Ecosystem

<details>
  <summary>Project Setup</summary>
  
  #### Initial Project setup 
  1. npm init -y   --> To initilaze package.json
  2. add noscript tag in the index.html to check if the user has disabled the javascript and show a message
  3. npm i --save-dev @babel/core @babel/cli @babel/preset-env @babel/preset-react --> to support ES6 feature s in old browsers and also to support JSX
  4. .babelrc -> to tell which babel plugins and presets to use to transpile the code
     * @babel/preset-env --> handles transpilation of ES6 to common Js
     * @babel/react --> Deals with JSX
  5. npm i react react-dom --> for react
  6. npm i --save-dev webpack webpack-cli webpack-dev-server style-loader css-loader babel-loader  --> webpack is used to actually build our app. Performs operations on our code
  7. npx webpack-dev-server --mode development --> to run webpack dev server
  8. npm i --save-dev react-hot-loader --> To load react app automatically
</details>

<details>
<summary>Adding Redux</summary>

#### Problem Redux is solving
1. Props Drilling
2. State management throughout the application

#### solution to the above problem
1. Maintaining a singl global source to share the state among all the components
2. But the problem is unrestricted access
3. So, Redux aims to provide global state with strict rules and organization to it

#### How does Redux works?
1. It has one central, global state called store that all our components can access
   
#### How does Redux maintain the global state?

- We have two other components
  - Redux actions -> is a json object which has a type and payload
  - Reducers -> what should happen to redux store when redux actions are performed

- Now to answer the question - Components can only interact with the state by triggering redux action 
  
#### Installing redux
- npm install redux react-redux

#### About connect

- connect is a higher order function
- it takes two parameters mapStateToProps, mapDispatchToProps
- connect(mapStateToProps, mapDispatchToProps)(componentName)
- Sometimes components may only need one of them
- when we call connect, state and dipatch function are passed as props to the component

#### Best practices for Redux
- Export unconnected(for unit tests) and connected components
- Keep Redux actions and async operations out of your reducers
- Think carefully about connecting components
</details>

<details>
<summary>Redux side effects</summary>

#### Dealing with Side effects of Redux
- Though we are using redux, there will some side effects like calling the async functions and all. These are called side effects
- To get over this, we use some kind of side effects of redux
- In this, we are going to use redux thunk
- npm i redux-thunk redux-devtools-extension @babel/runtime
- @babel/runtime --> for the async thunk
- npm i --save-dev @babel/plugin-transform-runtime
</details>

<details>
<summary>Selectors</summary>

#### Deriving the data in the structure we want
- selectors are used to provide the proper structure to our state in the redux
- Abstracting the state format, transforming the data
- npm i reselect
- Reselect is used to performing complex logic on the states
</details>

<details>
<summary>Styled Components</summary>

#### CSS in JS
- Allows to define css in js files
- npm i styled-components
</details>