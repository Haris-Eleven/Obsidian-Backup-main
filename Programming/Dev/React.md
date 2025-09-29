![[Development]]
1. It is a JS library 
2. JSX ( javascript xml ) markup syntax inside js 
>  *JSX lets you put markup into JavaScript. Curly braces let you “escape back” into JavaScript*
3. Unique **Key** attribute to all elements in a list 
# Hooks
1. Functions starting with `use` are called _Hooks_
2. Hooks let you **attach behavior** to functional components
> Think of hook like a function that gives you access to **React's internal Memory**
3. Hooks allow you to use state and other React features without **writing class components** 
# Babel
1. JSX -> JS
2. Modern JS -> Old JS
# Webpack 
1. Bundles all modules and contents into single JS file
# Vite
1. A modern **frontend build tool & development server** that *replaces Webpack + Babel* setups 
2. **Hot Module Replacement** (HMR) replaces module live 

# State Management
1. **State**: Think of state as the *minimal set of changing data* that your app needs to remember.
2. **Props** are like *arguments you pass a function*. They let a parent component pass data to a child component
3. **Context API** It is like a global store ( shared state across components )
	1. **Prop drilling** was a huge problem 
	2. Contexts provides a way to pass down data without having to pass props manually at every level in the component tree 
	3. Before the intro of hooks 
		1. *Create Context* : creates a store
		2. *Context Provider* : Provides the context to all the components
		3. *Use Context* : uses the provided context before hooks the consuming was complex
4. **useContext** : a better way to consume contexts 
5. **useReducer**: It is an alternative to useState (it is more primitive than useState )
	1. useState is built using useReducer 
	2. *what is a reducer* ? [[Javascript#Reducers]]
	3. `useReducer` is a React Hook for **managing complex state logic**
	4. why `useReducer` Can Be Better
		- `useReducer` helps you:
		- **Group related state** in one object    
		- **Centralize all update logic** in one function (the reducer)
		- **Handle complex updates more predictably**