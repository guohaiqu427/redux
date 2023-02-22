# redux

*Redux is a predictable state container for JavaScript apps.

It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. *

*Redux 是一个状态容器，独立于app之外有自己的环境*


## Install： 

library for use redux in react
`npm install react-redux`

redux library 
`npm install redux`


## Redux data flow 

![data-flow](Static/data-flow.jpeg)

## syntax 

1. import : 
	```js
	import {createStore} from "redux"

2. reducer: 
	```js 
		const initialState = {count: 0};
		function reducer (state = initialState, action) {
  			switch(action.type){
    			case "increment":
    			  	return { count: state.count + 1 }
   				 case "decrement":
    			  	return { count: state.count -1}
   				 default: 
      				return state
  			}
		}

3. store: 
	```js 
	const store = createStore(reducer)

4. case: 
	```js 
	const increment = {type:"increment"}
	const decrement = {type: "decrement"}
5. dispatch
	```js
	function Counter (){
  		return 	<div>
   			<button onClick={()=> {store.dispatch(increment)}}>+</button>
    		<span>{store.getState().count}</span>
    		<button onClick={()=> {store.dispatch(decrement)}}>-</button>
  			</div>
	}
6. render & update 
	```js
	store.subscribe(()=>{
  		root.render(
   		 <Counter />
 		);
	})

	root.render(
  		<Counter />
	);

