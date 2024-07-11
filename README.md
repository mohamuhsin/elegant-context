# Elegant Context

This project demonstrates the problem of <b>PROP DRILLING</b> in React and how to solve it.

## PROP DRILLING

Prop drilling involves passing of props down manually from component to component to where they
are needed.

The problem with prop drilling is that, as the application grows in complexity, 
passing data through multiple levels of components can become complex and error-prone.

## Context API 

Context API helps solve the challenges of prop drilling, it manages all the global state and data without passing
from one component to the next.

We use the createContext and useContext hooks to utilize context API functionality in our application.
createContext creates and setups the data thats needs to be shared while useContext helps unpack each at a component level 
whenever required which would be ideally be done with props forwarding. Context API cuts the path.


## Use of Context API in this project

A context names 'CartContext' has been created and used to provide context to manage items in the cart and functions as
handleAddItemToCart which adds item to the cart and handleUpdateCartItemQuantity quantity updates on items on cart.

Relying on prop dilling, this context data would be domiciled on the App() and passed manually as props from parent app down the chain
of components and utilized where needed.




