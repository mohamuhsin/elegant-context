# Elegant Context:

This project demonstrates the problem of <b>PROP DRILLING</b> in React and how to solve it.

## PROP DRILLING:

Prop drilling involves passing of props down manually from component to component to where they
are needed.

The problem with prop drilling is that, as the application grows in complexity, 
passing data through multiple levels of components can become complex and error-prone.

## Context API:

Context API helps solve the challenges of prop drilling, it manages all the global state and data without passing
from one component to the next.

We use the createContext and useContext hooks to utilize context API functionality in our application.
createContext creates and setups the data that needs to be shared while useContext helps unpack each global data or function at a component level
whenever required, this would be ideally be done with props forwarding of data and callback functions. 
Context API cuts the path making the app less complex and more maintainable.


### Use of Context API in this project:

A context named 'CartContext' has been created and used to provide context to manage items in the cart and functions as
handleAddItemToCart which adds item to the cart and handleUpdateCartItemQuantity quantity updates on items on cart.

Relying on prop dilling, this context data would be domiciled on the App() and passed manually as props from parent app down the chain
of components and utilized where needed.


### State management with useReducer Hook

The useReducer Hook works similar to useState to manage state in a react app. 

However, useReducer Hooks is best suited for complex state management in a more concise, predictable, optimized and maintainable way.
useState is the best suited for simple states changes in simple application.

### How to use useReducer

Here is how we use the hook, it replaces useState with.

```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

Description of the different parameters used with the useReducer Hook:
1. state: current value and is set to the initialState value during the initial render.
2. dispatch: a function that updates the state value and always triggers a re-render, just like the updater function in useState hook.
3. reducer: a function that houses all the logic of how the state gets updated. 
            The reducer function takes state and action as arguments and returns the next state.
4. initialState: houses the initial value and can be of any type.

### How to useReducer has been applied in this project

We used useState earlier in the project to manage the state of the shopping cart as follows:

```javascript
const [shoppingCart, setShoppingCart] = useState({
    items: [],
  });
```

The useReducer was later introduced to manage this state.
All handler functions logic was moved to the reducer function which is then triggered via the dispatch function called inside the handlers.

Example of adding item to cart using reducer:

```javascript
function handleAddItemToCart(id) {
    shoppingCartDispatch({
      type: "ADD_ITEM",
      payload: id,
    });
  }
```
All the logic has been moved the reducer function.

This is the common pattern on further implementation of other handler actions. i.e: call dispatch and pass a type of action to tell
the reducer how to alter state. The reducer uses if...else or switch case to determine which action has been triggered 
and then update the state accordingly

Have a look at the `shopping-cart-context.jsx` for further insights on implementation of state management with the useReducer Hook.




