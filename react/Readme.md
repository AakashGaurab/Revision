## what is react?

- React is an open-source JavaScript library developed by Facebook for building user interfaces (UIs). It is widely used for creating dynamic and interactive web applications. React follows a component-based architecture, where UIs are divided into reusable components.
- The key features of React include:
    - **Component-Based**: React allows developers to create modular UI components that can be reused throughout an application. Each component manages its own state and can be composed together to build complex UIs.

    - **Virtual DOM**: React uses a virtual representation of the actual DOM (Document Object Model) called the Virtual DOM. This virtual representation allows React to efficiently update and render only the components that have changed, rather than re-rendering the entire page. This approach improves performance and provides a smoother user experience.

    - **Declarative Syntax**: React uses a declarative syntax, which means you describe how the UI should look based on its state, and React takes care of updating the actual UI to match the desired state. This makes it easier to reason about and maintain the application's UI.

    - **One-Way Data Flow**: React enforces a one-way data flow, which means data in React applications flows in a single direction. This helps to maintain a predictable state management and simplifies debugging.

    - **React Hooks**: Hooks were introduced in React 16.8 as a way to add state and other React features to functional components. They allow developers to reuse stateful logic and reduce the reliance on class components.

- React can be used to build single-page applications (SPAs), mobile applications, and even desktop applications using frameworks like React Native and Electron. It has a large and active community, which means there are abundant resources, libraries, and tools available to support React development.



## React benefits:

- React is **fast**. Apps made in React can handle complex updates and still feel quick and responsive.
- React is **modular**. Instead of writing large, dense files of code, you can write many smaller, reusable files. 
- React is **scalable**. Large programs that display a lot of changing data are where React performs best.
- React is **flexible**. You can use React for interesting projects that have nothing to do with making a web app. People are still     figuring out React’s potential
- React is **popular**. While this reason has admittedly little to do with React’s quality, the truth is that understanding React will make you more employable.




## What is JSX?

- JSX is a syntax extension for JavaScript. It was written to be used with React. JSX code looks a lot like HTML.
    ```javascript
            const navBar = <nav>I am a nav bar</nav>;
- JSX is not valid JavaScript. Web browsers can’t read it!
- If a JavaScript file contains JSX code, then that file will have to be compiled. This means that before the file reaches a web browser, a JSX compiler will translate any JSX into regular JavaScript.
- JSX elements are treated as JavaScript expressions. They can go anywhere that JavaScript expressions can go. This means that a JSX element can be saved in a variable, passed to a function, stored in an object or array… you name it.
- JSX elements can have attributes, just like how HTML elements can.
- If a JSX expression takes up more than one line, then you must wrap the multi-line JSX expression in parentheses
    ```javascript
        (
            <a href="https://www.example.com">
                <h1>
                Click me!
                </h1>
            </a>
        )
- JSX expression must have exactly one outermost element.

- In HTML, it’s common to use class as an attribute name, but In JSX, you can’t use the word class! You have to use className instead:
    ```javascript
        <h1 className="big">Title</h1>

- Any code in between the tags of a JSX element will be read as JSX, not as regular JavaScript! JSX doesn’t add numbers—it reads them as text, just like HTML.You need a way to write code that says, “Even though I am located in between JSX tags, treat me like ordinary JavaScript and not like JSX.” , You can do this by wrapping your code in curly braces.
    ```javascript
    root.render(<h1>{2 + 3}</h1>);

- Variable Attributes in JSX :
    ```javascript
        const pics = {
        panda: "http://bit.ly/1Tqltv5",
        owl: "http://bit.ly/1XGtkM3",
        owlCat: "http://bit.ly/1Upbczi"
        }; 
        
        const panda = (
        <img 
            src={pics.panda} 
            alt="Lazy Panda" />
        );

- Event Listeners in JSX:
    ```javascript
        function clickAlert() {
        alert('You clicked this image!');
        }
        
        <img onClick={clickAlert} />
- In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.

- JSX Conditionals: The Ternary Operator:
    ```javascript
    const headline = (
        <h1>
            { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
        </h1>
        );


- .map in JSX
     ```javascript
        const strings = ['Home', 'Shop', 'About Me'];
        const listItems = strings.map(string => <li>{string}</li>);
        <ul>{listItems}</ul>

- Keys:
    - A key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute
    - keys don’t do anything visible! React uses them internally to keep track of lists. If you don’t use keys when you’re supposed to, React might accidentally scramble your list items into the wrong order.
    - Not all lists need to have keys. A list needs keys if either of the following is true:
        - The list items have memory from one render to the next. For instance, when a to-do list renders, each item must “remember” whether it was checked off. The items shouldn’t get amnesia when they render.
        - A list’s order might be shuffled. For instance, a list of search results might be shuffled from one render to the next.
    - If neither of these conditions is true, then you don’t have to worry about keys. If you aren’t sure, then it never hurts to use them!
    ```javascript
            <ul>
            <li key="li-01">Example1</li>
            <li key="li-02">Example2</li>
            <li key="li-03">Example3</li>
            </ul>




## The Virtual DOM

- DOM manipulation is the heart of the modern, interactive web. Unfortunately, it is also a lot slower than most JavaScript operations.
- This slowness is made worse by the fact that most JavaScript frameworks update the DOM much more than they have to.
- As an example, let’s say that you have a list that contains ten items. You check off the first item. Most JavaScript frameworks would rebuild the entire list. That’s ten times more work than necessary! Only one item changed, but the remaining nine get rebuilt exactly how they were before.
- Rebuilding a list is no big deal to a web browser, but modern websites can use huge amounts of DOM manipulation. Inefficient updating has become a serious problem.
- To address this problem, the people at React popularized something called the virtual DOM.

- In React, for every DOM object, there is a corresponding “virtual DOM object.” A virtual DOM object is a representation of a DOM object, like a lightweight copy.
- A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen.
- When you render a JSX element, every single virtual DOM object gets updated.Once the virtual DOM has been updated, then React compares the virtual DOM with a virtual DOM snapshot that was taken right before the update.By comparing the new virtual DOM with a pre-update version, React figures out exactly which virtual DOM objects have changed. This process is called “diffing.”
- Once React knows which virtual DOM objects have changed, then React updates those objects, and only those objects, on the real DOM.




## React Components:
 
- A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML and re-render it when some data changes.
    ```javascript
        function MyComponent() {
        return <h1>Hello world</h1>;
        }
        
        ReactDOM.createRoot(
        document.getElementById('app')
        ).render(<MyComponent />);
- If you are creating a component, be sure to name it starting with a capital letter so it interprets it as a React component. If it begins with a lowercase letter, React will begin looking for a built-in component such as div and input instead and fail.



## Using and Rendering a Component
 - index.html file:
    ```javascript
            // index.html
            <!DOCTYPE html>
            <html lang="en">
            <head>
                <meta charset="UTF-8">
                <meta name="viewport" content="width=device-width, initial-scale=1.0">
                <link rel="stylesheet" href="style.css">
            </head>
            <body>
            <main id="app">
            </main>
            <script src="/index.compiled.js"></script>
            </body>
            </html>
        ```
- index.js
    ```javascript
           import React from 'react';
            import ReactDOM from 'react-dom/client';

            import MyComponent from './App';
            ReactDOM.createRoot(document.getElementById('app')).render(<MyComponent />)

- app.js
    ```javascript
        import React from 'react';
        function MyComponent() {
        return <h1>Hello world</h1>;
        }

        export default MyComponent;



## props

- Information that gets passed from one component to another is known as props.
- Props can be used to customize the output of each component depending on the information that is passed in.
    #### Access a Component's props
    - A component’s props is an object. It holds information about that component.
    - example:
        ```javascript
            // product.js
            import React from 'react';
            function Product(props) {
            return (
                <div>
                <h1>{props.name}</h1>
                <h2>{props.price}</h2>
                <h3>{props.rating}</h3>
                </div>       
            );
            }
            export default Product;
        ```
    - app.js
        ```javascript
            //app.js
            import React from 'react';
            import Product from './Product'

            function App() {
            return <Product name="Apple Watch" price = {399} rating = "4.5/5.0" />;
            }

            export default App;
        ```

#### Render Different UI Based on props

-   ```javascript
        function LoginMsg(props) {
            if (props.password === 'a-tough-password') {
                return <h2>Sign In Successful.</h2>
            } else {
                return <h2>Sign In Failed..</h2>
            }
        }
    ```

#### Pass an Event Handler as a prop

-   ```javascript
        //talker.js
            import React from 'react';
            import Button from './Button';

            function Talker() {
            function talk() {
                let speech = '';
                for (let i = 0; i < 10000; i++) {
                speech += 'blah ';
                }
                alert(speech);
                }
            return <Button talk={talk}/>;
            }

            export default Talker;
    
            //button.js
            import React from 'react';
            function Button(props) {
            return (
                <button onClick={props.talk}>
                Click me!
                </button>
            );
            }

            export default Button;
    ```


#### props.children
- Every component’s props object has a property named children.
- props.children will return everything in between a component’s opening and closing JSX tags.
- props.children would return everything in between <MyFunctionComponent> and </MyFunctionComponent>.
- If a component has more than one child between its JSX tags, then props.children will return those children in an array. However, if a component has only one child, then props.children will return the single child, not wrapped in an array
    ```javascript
        //example-1
        <BigButton>
            I am a child of BigButton.
        </BigButton>

        //props.children would equal the text, “I am a child of BigButton.”
    ```
    ```javascript
        //example-1
            <BigButton>
                <LilButton />
            </BigButton>
         //props.children would equal a <LilButton /> component.
    ```
    ```javascript
        //example-3
        <BigButton />

#### Giving Default Values to props

   -  ```javascript
        function Example({text='This is default text'}) {
            return <h1>{text}</h1>
        }




## Hooks:
### Why Use Hooks?
- React Hooks, plainly put, are functions that let us manage the internal state of components and handle post-rendering side effects directly from our function components. Using Hooks, we can determine what we want to show the users by declaring how our user interface should look based on the state. 

- Before Hooks, function components were only used to accept data in the form of props and return some JSX to be rendered. The State Hook allows us to manage dynamic data, in the form of component state, within our function components

- React offers a number of built-in Hooks. A few of these include useState(), useEffect(), useContext(), useReducer(), and useRef(). See the full list in the React docs.

### Use State :

- When we call the useState() function, it returns an array with two values:
        - The current state: The current value of this state.
        - The state setter: A function that we can use to update the value of this state.
        ```javascript
            const [currentState, setCurrentState] = useState();
        ```
    - Example: 
    ```javascript
        import React, { useState } from "react";
 
        function Toggle() {
            const [toggle, setToggle] = useState();
                return (
                    <div>
                    <p>The toggle is {toggle}</p>
                    <button onClick={() => setToggle("On")}>On</button>
                    <button onClick={() => setToggle("Off")}>Off</button>
                    </div>
                );
        }
    ```
    - setToggle(), is called by our onClick event listeners. To update the value of toggle and re-render this component with the new value, all we need to do is call the setToggle() function with the next state value as an argument.
    - With the State Hook, updating the state is as simple as calling a state setter function. Calling the state setter signals to React that the component needs to re-render, so the whole function defining the component is called again. The magic of useState() is that it allows React to keep track of the current value of the state from one render to the next!


    #### Initialize State
    - Like how you used the State Hook to manage a variable with string values, we can use the State Hook to manage the value of any primitive data type and even data collections like arrays and objects!
    - Example:
    ```javascript
        import React, { useState } from 'react';
 
        function ToggleLoading() {
        const [isLoading, setIsLoading] = useState();
        
        return (
            <div>
            <p>The data is {isLoading ? 'Loading' : 'Not Loading'}</p>
            <button onClick={() => setIsLoading(true)}>
                Turn Loading On
            </button>
            <button onClick={() => setIsLoading(false)}>
                Turn Loading Off
            </button>
            </div>
        );
    ```

    #### Use State Setter Outside of JSX:
    ```javascript
        import React, { useState } from "react";

        // regex to match numbers between 1 and 10 digits long
        const validPhoneNumber = /^\d{1,10}$/;

        export default function PhoneNumber() {
        const [phone, setPhone] = useState("");

        const handleChange = ({ target }) => {
            const newPhone = target.value;
            const isValid = validPhoneNumber.test(newPhone);
            if (isValid) {
            setPhone(newPhone);
            }
            else{
            setPhone('')
            }
            // just ignore the event, when new value is invalid
        };

        return (
            <div className="phone">
            <label for="phone-input">Phone: </label>
            <input value={phone} onChange={handleChange} id="phone-input" />
            </div>
        );
    }
    ```


    #### Set From Previous State
    -  React state updates are asynchronous. This means that there are some scenarios where portions of your code will run before the state is finished updating.

    - This is a good and a bad thing! Grouping the state updates together can improve performance in your application, but it can result in outdated state values. Consequently, it is best practice to update a state with a callback function, preventing accidental outdated values.

    - Let’s take a look at the following code to see how it’s done:

    ```javascript
        import React, { useState } from 'react';
 
        export default function Counter() {
        const [count, setCount] = useState(0);
        
        const increment = () => setCount(prevCount => prevCount + 1);
        
        return (
            <div>
            <p>Wow, you've clicked that button: {count} times</p>
            <button onClick={increment}>Click here!</button>
            </div>
        );
        }
    ```
    - When the button is pressed, the increment() event handler is called. Inside this function, we use our setCount() state setter with a callback function.
    - Because the next value of count depends on the previous value of count, we pass a callback function as the argument for setCount() instead of a value .
    - When our state setter calls the callback function, this state setter callback function takes our previous count as an argument. The value returned by this state setter callback function is used as the next value of count (in this case, prevCount + 1).
    - We can also just call setCount(count +1) and it would work the same in this example, but it is safer to use the callback method.



    #### Arrays in State
    ```javascript
        import React, { useState } from 'react';
 
        //Static array of pizza options offered. 
        const options = ['Bell Pepper', 'Sausage', 'Pepperoni', 'Pineapple'];
        
        export default function PersonalPizza() {
        const [selected, setSelected] = useState([]);
 
        const toggleTopping = ({target}) => {
            const clickedTopping = target.value;
            setSelected((prev) => {
            // check if clicked topping is already selected
            if (prev.includes(clickedTopping)) {
                // filter the clicked topping out of state
                return prev.filter(t => t !== clickedTopping);
            } else {
                // add the clicked topping to our state
                return [clickedTopping, ...prev];
            }
            });
        };
        
        return (
            <div>
            {options.map(option => (
                <button value={option} onClick={toggleTopping} key={option}>
                {selected.includes(option) ? 'Remove ' : 'Add '}
                {option}
                </button>
            ))}
            <p>Order a {selected.join(', ')} pizza</p>
            </div>
        );
        }
    ```
    - In the above example, we are using two arrays:
        - The options array contains the names of all of the pizza toppings available.
        - The selected array represents the selected toppings for our personal pizza.
    - The options array contains static data, meaning that it does not change. It’s best practice to define static data models outside of function components since they don’t need to be recreated each time our component re-renders. In our JSX, we use the JavaScript .map() method to render a button for each of the toppings in our options array.
    - The selected array contains dynamic data, meaning that it changes, usually based on a user’s actions. We initialize selected as an empty array. When a button is clicked, the toggleTopping() event handler is called. Notice how this event handler uses information from the event object to determine which topping was clicked.
    - When updating an array in a state, we do not just add new data to the previous array. We replace the previous array with a brand new array. This means that any information that we want to save from the previous array needs to be explicitly copied over to our new array. That’s what this spread syntax does for us: ...prev.
    - Notice how we use the .includes(), .filter(), and .map() methods of our arrays. If these are new to you, or you just want a refresher, take a minute to review these array methods. We don’t need to be full-fledged JavaScript gurus to build React applications but know that investing time to strengthen our JavaScript skills will always help us do more faster (and have a lot more fun doing it) as React developers.


    #### Objects in State

    ```javascript
        export default function Login() {
        const [formState, setFormState] = useState({});
        const handleChange = ({ target }) => {
            const { name, value } = target;
            setFormState((prev) => ({
            ...prev,
            [name]: value
            }));
        };
        const handleSubmit = (event) => {
            event.preventDefault();
            alert(JSON.stringify(formState, '', 2));
        };
                
        return (
            <form onSubmit={handleSubmit}>
            <input
                value={formState.firstName}
                onChange={handleChange}
                name="firstName"
                type="text"
            />
            <input
                value={formState.password}
                onChange={handleChange}
                type="password"
                name="password"
            />
            </form>
        );
        }
    ```
    - A few things to notice:
        - We use a state setter callback function to update a state based on the previous value.
        - The spread syntax is the same for objects as for arrays: { ...oldObject, newKey: newValue }.
        - We reuse our event handler across multiple inputs by using the input tag’s name attribute to identify which input the change event came from.
    - Once again, when updating the state with setFormState() inside a function component, we do not modify the same object. We must copy over the values from the previous object when setting the next value of a state. Thankfully, the spread syntax makes this super easy to do!
    - Anytime one of the input values is updated, the handleChange() function will be called. Inside this event handler, we use object destructuring to unpack the target property from our event object, then we use object destructuring again to unpack the name and value properties from the target object.
    
    

### useEffect:
- There are three key moments when the Effect Hook can be utilized:
    - When the component is first added, or mounted, to the DOM and renders.
    - When the state or props change, causing the component to re-render.
    - When the component is removed, or unmounted, from the DOM.

- In simple terms, the effect in React is a way to perform certain actions after a component has been rendered or when its dependencies have changed. It allows you to handle side effects like fetching data from an API, updating the document title, subscribing to events, or any other actions that are not directly related to rendering the component.

- The effect is a function that you define inside a React component using the useEffect hook. This function will be executed automatically by React after the component has been rendered.

- The useEffect hook takes two arguments: the first argument is the function that contains the side effect code, and the second argument is an optional array of dependencies. The dependencies specify the values that the effect depends on. If any of the dependencies change, the effect will be triggered again.

- Suppose we want to allow a user to change the title of the web page tab every time they type. We can implement this with the Effect Hook (useEffect()) like so:
    ```javascript
        import React, { useState, useEffect } from 'react';

        function PageTitle() {
        const [name, setName] = useState('');
        
        useEffect(() => {
            document.title = `Hi, ${name}`;
        });
        
        return (
            <div>
            <p>Use the input field below to rename this page!</p>
            <input onChange={({target}) => setName(target.value)} value={name} type='text' />
            </div>
        );
        }
    ```
    - The useEffect() function has no return value as the Effect Hook is used to call another function. We pass the callback function, or effect, to run after a component renders as the argument of the useEffect() function. In our example, the following effect runs after each time the PageTitle component renders:
        ```javascript 
            () => { document.title = `Hi, ${name}`;}
        ```
    - The onChange event listener triggers the PageTitle component to be re-rendered every time the user types in the input. Consequently, this triggers useEffect() and changes the document’s title.
    

    #### Clean Up Effects

    - Some effects require cleanup. For example, we might want to add event listeners to some element in the DOM, beyond the JSX in our component. When we add event listeners to the DOM, it is important to remove those event listeners when we are done with them to avoid memory leaks!
    - Let’s consider the following effect:
        ```javascript
            useEffect(()=>{
                document.addEventListener('keydown', handleKeyPress);
                // Specify how to clean up after the effect:
                return () => {
                    document.removeEventListener('keydown', handleKeyPress);
                };
        ```
    - If our effect didn’t return a cleanup function, a new event listener would be added to the DOM’s document object every time that our component re-renders. Not only would this cause bugs, but it could cause our application performance to diminish and maybe even crash!

    - Because effects run after every render and not just once, React calls our cleanup function before each re-render and before unmounting to clean up each effect call.

    - If our effect returns a function, then the useEffect() Hook always treats that as the cleanup function. React will call this cleanup function before the component re-renders or unmounts. Since this cleanup function is optional, it is our responsibility to return a cleanup function from our effect when our effect code could create memory leaks.


    #### Control When Effects Are Called

    - we want to skip calling our effect on re-renders altogether.
    - It is common, when defining function components, to run an effect only when the component mounts (renders the first time), but not when the component re-renders. The Effect Hook makes this very easy for us to do! If we want to only call our effect after the first render, we pass an empty array to useEffect() as the second argument. This second argument is called the dependency array.

    - The dependency array is used to tell the useEffect() method when to call our effect and when to skip it. Our effect is always called after the first render but only called again if something in our dependency array has changed values between renders.

    - Example
        ```javascript
            useEffect(() => {
            alert("component rendered for the first time");
            return () => {
                alert("component is being removed from the DOM");
            };
            }, []); 
        ```
    - Without passing an empty array as the second argument to the useEffect() above, those alerts would be displayed before and after every render of our component, which is clearly not when those messages are meant to be displayed. Simply passing [] to the useEffect() function is enough to configure when the effect and cleanup functions are called!


    #### Fetch Data
    - When our effect is responsible for fetching data from a server, we pay extra close attention to when our effect is called. Unnecessary round trips back and forth between our React components and the server can be costly in terms of:
        - Processing
        - Performance
        - Data usage for mobile users
        - API service fees

    - When the data that our components need to render doesn’t change, we can pass an empty dependency array so that the data is fetched after the first render. When the response is received from the server, we can use a state setter from the State Hook to store the data from the server’s response in our local component state for future renders. Using the State Hook and the Effect Hook together in this way is a powerful pattern that saves our components from unnecessarily fetching new data after every render!
    - An empty dependency array signals to the Effect Hook that our effect never needs to be re-run, that it doesn’t depend on anything. Specifying zero dependencies means that the result of running that effect won’t change and calling our effect once is enough.
    - A dependency array that is not empty signals to the Effect Hook that it can skip calling our effect after re-renders unless the value of one of the variables in our dependency array has changed. If the value of a dependency has changed, then the Effect Hook will call our effect again!

    - Example
        ```javascript
            useEffect(() => {
            document.title = `You clicked ${count} times`;
            }, [count]); // Only re-run the effect if the value stored by count changes
        ```
    

    #### Separate Hooks for Separate Effects
    ```javascript
        // Handle menuItems with one useEffect hook.
        const [menuItems, setMenuItems] = useState(null);
        useEffect(() => {
        get('/menu').then((response) => setMenuItems(response.data));
        }, []);
        
        // Handle position with a separate useEffect hook.
        const [position, setPosition] = useState({ x: 0, y: 0 });
        useEffect(() => {
        const handleMove = (event) =>
            setPosition({ x: event.clientX, y: event.clientY });
        window.addEventListener('mousemove', handleMove);
        return () => window.removeEventListener('mousemove', handleMove);
        }, []);
    ```


# What are hooks?
- React Hooks are a new addition to React that were introduced in React 16.8. They allow you to use state and other React features without writing a class [0]. Hooks are functions that let you "hook into" React state and lifecycle features from function components. They work by allowing you to use React without classes, providing a more direct API to the React concepts you already know [6].

Here are some key points about React Hooks:

Hooks are a new addition to React that were introduced in version 16.8 [0].

They allow you to use state and other React features without writing a class [0].
Hooks are functions that let you "hook into" React state and lifecycle features from function components [6].
They are completely opt-in and don't contain any breaking changes [0].
Hooks provide a more direct API to the React concepts you already know, such as props, state, context, refs, and lifecycle [0].
They offer a new powerful way to combine these concepts [0].
With React Hooks, you can use functional components for almost everything, from rendering UI to handling state and logic [9].
Hooks allow you to reuse stateful logic between components without changing their architecture or structure [9].
They make it easier to understand and manage complex components by allowing you to separate them into smaller functions based on related functionality [9].
Hooks eliminate the need to use classes in React, making it easier to learn and use React features without having to understand class syntax [9].
There are several built-in React Hooks, such as useState, useEffect, useReducer, useCallback, useMemo, useRef, useLayoutEffect, and useDebugValue [3].


Let's take a closer look at some of the basic React Hooks:

- useState: This Hook allows you to add state to your functional components. It returns a stateful value and an updater function to update it [3].
- useEffect: This Hook allows you to perform side effects in your functional components, such as fetching data from an API or subscribing to events. It runs after every render and can be used to manage subscriptions, timers, mutations, and more [3].
useReducer: This Hook is an alternative to useState that helps with complex state management. It returns a stateful value and a dispatch function to update it [3].
- useCallback: This Hook returns a memoized version of a callback function. It can be used to prevent unnecessary re-renders of child components that depend on the callback [3].
- useMemo: This Hook returns a memoized value that helps with performance optimizations. It can be used to avoid expensive calculations on every render [3].
useRef: This Hook returns a ref object with a .current property. The ref object is mutable and can be used to access a child component imperatively [3].
- useLayoutEffect: This Hook is similar to useEffect, but it fires synchronously after all DOM mutations. It's best to use useEffect as much as possible and only use useLayoutEffect when necessary [3].
useDebugValue: This Hook helps to display a label in React DevTools for custom hooks. It can be used to provide additional debugging information [3].
These are just a few examples of the built-in React Hooks. There are many more hooks available that can be used to solve specific problems or optimize your components. Additionally, you can also create your own custom hooks to encapsulate reusable logic [3].

It's worth noting that while React Hooks provide a more concise and functional way of writing components, there are no plans to remove classes from React. Hooks are completely opt-in, and you can choose to use them in your new components while still using classes in your existing codebase if you prefer [2].

In conclusion, React Hooks are a powerful addition to React that allow you to use state and other React features in function components without writing a class. They provide a more direct API to React concepts and offer a more ergonomic way to build components. With built-in hooks like useState and useEffect, you can add state and perform side effects in your functional components. Additionally, you can create your own custom hooks to encapsulate reusable logic. While Hooks replace the need for classes in many cases, classes are still supported in React and can be used alongside Hooks if desired.


# What are useEffect and useRef?
- The useEffect and useRef are two important React Hooks that serve different purposes.

useEffect is a hook that allows you to perform side effects in your functional components. It is similar to the lifecycle methods in class components. You can use useEffect to manage subscriptions, perform data fetching, manipulate the DOM, or any other side effect that needs to be executed after rendering 

- useRef is a hook that returns a mutable ref object. It allows you to create a reference to a DOM element or any other value that persists across renders [3]. The ref object has a .current property that can be used to access the current value of the ref

 import React, { useRef } from 'react';

function Example() {
  const inputRef = useRef();

  const handleFocus = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
}
In this example, the useRef hook is used to create a ref object called inputRef. The ref object is then attached to the input element using the ref attribute. When the button is clicked, the handleFocus function is called, which uses the .current property of the inputRef to access the input element and call the focus() method to focus the input



# how to merge data in useState  in react ?
- Using the spread operator (...): The spread operator can be used to merge arrays or objects. When merging arrays, you can use the spread operator to create a new array that includes all the elements from the existing array as well as the new elements. When merging objects, you can use the spread operator to create a new object that includes all the properties from the existing object as well as the new properties.

Here's an example of merging an array using the spread operator:

   const [array, setArray] = useState([1, 2, 3]);

   const mergeArray = () => {
     setArray(prevArray => [...prevArray, 4, 5]);
   };
In this example, the mergeArray function updates the array state by creating a new array that includes all the elements from the existing array as well as the new elements [4, 5].

Here's an example of merging an object using the spread operator:

 const [object, setObject] = useState({ name: 'John', age: 25 });

   const mergeObject = () => {
     setObject(prevObject => ({ ...prevObject, gender: 'Male' }));
   };
In this example, the mergeObject function updates the object state by creating a new object that includes all the properties from the existing object as well as the new property gender: 'Male'.


# what is react lifecycle ?
- The React lifecycle refers to a series of events or methods that occur during the birth, growth, and death of a React component. These methods allow you to control and manipulate the component at different stages. The React lifecycle can be divided into three main phases: Mounting, Updating, and Unmounting. Let's explore each phase in detail:

- Mounting:
This phase occurs when a component is being inserted into the DOM for the first time.

The following lifecycle methods are called in this phase:

constructor(): This method is called when the component is being initialized and allows you to set the initial state and props of the component.

render(): This method is responsible for rendering the component's JSX and returning the elements that will be displayed on the screen.

componentDidMount(): This method is called after the component has been mounted in the DOM. It is commonly used for performing side effects, such as fetching data from an API or setting up event listeners.

- Updating:
This phase occurs when a component is being re-rendered due to changes in its props or state.
The following lifecycle methods are called in this phase:
render(): This method is called again to re-render the component with the updated props or state.

componentDidUpdate(prevProps, prevState): This method is called after the component has been re-rendered. It allows you to perform side effects based on the updated props or state. You can also compare the previous props and state with the current props and state to determine if any specific action needs to be taken.

- Unmounting:
This phase occurs when a component is being removed from the DOM.

The following lifecycle method is called in this phase:

componentWillUnmount(): This method is called right before the component is unmounted from the DOM. It is commonly used for cleaning up any resources or event listeners that were set up in the componentDidMount() method.

#  How useEffect is used  for cleaning event listeners or subscriptions ( like socket.io events) let’s see how we can implement that.
- Set up a single socket event handler and use functional updates for state: In this approach, you would use an empty dependency array for useEffect and avoid referencing the state directly within the effect. Instead, use functional updates to update the state. This ensures that you are always working with the latest version of the state and avoids referencing an old version of the state when re-rendering occurs. This approach is suitable if you can easily update the state using functional updates. Here's an example:

  
React.useEffect(() => {
  const handler = (message) => {
    // handle the message
  };
  
  socket.on('message', handler);
  
  return () => {
    socket.off('message', handler);
  };
}, []);

- Set up a new socket event handler with each change to state: In this approach, you create a new socket event handler every time the state changes. This ensures that each event handler is using the correct version of the state. However, it also means that you need to remove the previous event handler to avoid having multiple event handlers. This approach provides more flexibility in how you can use the state, but it can feel clunky due to the repeated setup and teardown of event handlers. Here's an example:
React.useEffect(() => {
  const handler = (message) => {
    // handle the message using the latest version of the state
  };
  
  socket.on('message', handler);
  
  return () => {
    socket.off('message', handler);
  };
}, [participants]);

# The order of hooks
A very important thing we have to understand is that we can’t change the order or numbers of the hooks in each render. It must be the same in every render. That means we can’t use conditional hooks. For e.g

if (item) {
    useEffect(() => {}) // you can't do this
}
or this 
items.forEach(() => useEffect(() => {}))
// because if the length of items changes the useEffect count will not be same in the next render.


# What is Memoization?
- Memoization in React refers to the process of optimizing React components by caching their results and preventing unnecessary re-renders. React provides several tools for memoization, such as React.memo(), useMemo(), and useCallback().

- One way to memoize a functional component in React is by using the React.memo() higher-order component. When you wrap a component with React.memo(), it performs a shallow comparison of the component's props to determine if it needs to be re-rendered. If the props haven't changed, the memoized component reuses the previously memoized values and skips the re-render. Here's an example:

function Comments({ name, comment, likes }) {
  return (
    <div>
      <p>{name}</p>
      <p>{comment}</p>
      <p>{likes}</p>
    </div>
  );
}

const MemoizedComment = React.memo(Comments);
In the above example, the MemoizedComment component will only re-render if its props (name, comment, likes) have changed. Otherwise, it will reuse the memoized values and skip the re-render.

- If you want to have more control over the comparison of props, you can provide a custom comparison function as the second argument to React.memo(). This function receives the previous props and the next props as arguments and should return true if the props are equal and false otherwise. Here's an example:

function checkCommentProps(prevProps, nextProps) {
  return (
    prevProps.name === nextProps.name &&
    prevProps.comment === nextProps.comment &&
    prevProps.likes === nextProps.likes
  );
}

const MemoizedComment = React.memo(Comments, checkCommentProps);
In this example, the MemoizedComment component will only re-render if the name, comment, or likes props have changed.

- Apart from React.memo(), React also provides the useMemo() and useCallback() hooks for memoization within functional components. These hooks allow you to memoize the values returned by a function or the function itself, respectively. By memoizing these values, you can avoid re-computing them on every render, optimizing performance. Here's an example:

const memoizedValue = React.useMemo(() => expensiveFunction(), [dependency]);

const memoizedCallback = React.useCallback(() => {
  // function body
}, [dependency]);
In the above example, useMemo() memoizes the result of the expensiveFunction() based on the dependency array. The memoized value will only be recalculated if the dependency changes. Similarly, useCallback() memoizes the callback function itself, ensuring that it remains the same across renders unless the dependency changes.

- It's important to note that memoization should only be applied to components or values that are actually performance bottlenecks. Applying memoization indiscriminately can introduce unnecessary complexity and overhead. React is already optimized to handle many rendering scenarios efficiently, so memoization should be used judiciously for specific cases where it provides a noticeable performance improvement.


 # Difference between shallow copy and deep copy?
 - Shallow Copy: A shallow copy creates a new object and copies the values of the original object's fields into the new object. However, if the original object contains references to other objects, the references are copied rather than creating new copies of the referred objects. This means that both the original object and the shallow copy share the same references to the nested objects. If any changes are made to the nested objects, both the original and the shallow copy will reflect those changes. Shallow copy is a relatively simple way to create copies, but it can lead to unexpected behavior if the shared references are modified.

- Deep Copy: A deep copy, on the other hand, creates a new object and recursively copies all the fields and nested objects of the original object. Instead of copying references, a deep copy creates new instances of the referred objects. This means that the new copy is completely independent of the original object and any changes made to the nested objects will not affect the original object or any other copies. Deep copy ensures that each copy has its own separate memory space and is useful when you want to create a completely independent copy of an object.

- To summarize, the main difference between shallow copy and deep copy is how they handle nested objects or references. Shallow copy copies the references, while deep copy creates new instances of the referred objects.

- It's important to note that the implementation of shallow copy and deep copy can vary depending on the programming language and the specific data structures being used. Some languages provide built-in mechanisms for performing shallow or deep copies, while in others, you may need to implement the copying logic yourself.

# What is the difference between FrameWork and Library?
- A library is a collection of pre-compiled functions or modules that can be called by developers at their discretion. It provides specific functionalities that can be used in various parts of an application. When using a library, the control flow remains with the developer, who decides when and where to call the library functions. The library is essentially a tool that developers can leverage to perform specific tasks or operations. Libraries are typically focused on solving a particular problem or providing a set of utilities.

- On the other hand, a framework is a more comprehensive and opinionated piece of software. It provides a structure and a set of conventions for building applications. A framework defines the overall architecture and flow of an application, requiring developers to follow its guidelines and patterns. It often provides a skeleton or a blueprint for the application, with hooks and callbacks that developers fill in to customize the behavior. The control flow in a framework is inverted compared to a library. The framework dictates when and where the developer's code should be executed. Developers work within the framework's boundaries and extend its functionality according to their specific needs. Frameworks are typically larger in scope and cover multiple aspects of application development.

- In summary, a library provides specific functionalities that developers can use at their discretion, while a framework provides a structure and conventions that developers must follow, with the framework controlling the overall flow of the application.



  # What are Promises and its states?
  - Promises in JavaScript are objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises have three different states: pending, fulfilled, and rejected.

- Pending: This is the initial state of a promise. It represents that the asynchronous operation is still ongoing and the promise has not yet been fulfilled or rejected.
- Fulfilled: When a promise resolves successfully, it enters the fulfilled state. This means that the asynchronous operation has been completed successfully and the promise has a resulting value. Once a promise is fulfilled, it becomes immutable, meaning it cannot change its state again.
- Rejected: If an error occurs during the asynchronous operation, the promise enters the rejected state. This indicates that the operation has failed and the promise contains an error value or reason for the failure. Like the fulfilled state, once a promise is rejected, it is immutable.


# What are the lifecycle methods in function based react?
- In function-based React components, the traditional lifecycle methods from class-based components are not available. Instead, React provides a new set of lifecycle methods in the form of hooks. Hooks are functions that allow you to add state and other React features to functional components.

Here are some commonly used hooks that correspond to the lifecycle methods in class-based components:

useEffect: This hook allows you to perform side effects in function components. It combines the functionality of multiple lifecycle methods, such as componentDidMount, componentDidUpdate, and componentWillUnmount. You can use useEffect to run code after the component has rendered, and to clean up resources when the component is unmounted.

useLayoutEffect: This hook is similar to useEffect, but it runs synchronously after all DOM mutations. It is often used when you need to measure the layout of components or make DOM updates immediately after the render.

useMemo: This hook allows you to memoize the result of a function and cache it until the dependencies change. It is similar to the shouldComponentUpdate lifecycle method, as it helps optimize performance by avoiding unnecessary re-renders.

useCallback: This hook is used to memoize functions and prevent unnecessary re-creation of functions on each render. It is similar to useMemo, but specifically for functions.

useRef: This hook allows you to create a mutable value that persists across renders. It is similar to the instance variables in class-based components and can be used to store references to DOM elements or other mutable values.

useState: This hook allows you to add state to functional components. It replaces the setState method in class-based components and returns a state value and a function to update that state.
These hooks provide a more concise and flexible way to manage component lifecycles in function-based React components. They allow you to handle side effects, manage state, and optimize performance without the need for class-based components.

It's worth noting that hooks were introduced in React 16.8 and have become the recommended way to handle component lifecycles in functional components.

# what is try catch error handling ?
- The try...catch statement is used in programming languages like JavaScript and SQL to handle runtime errors. It allows you to try running a block of code and catch any errors that occur during its execution. Here's an explanation of how try...catch works in both JavaScript and SQL:

In JavaScript: The try...catch syntax in JavaScript consists of two main blocks: try and catch. The code within the try block is executed, and if an error occurs, the execution is immediately stopped, and control is transferred to the catch block. The catch block contains the error handling code, where you can specify how to handle the error. The error object, typically named err, contains information about the error, such as its type and message. Here's an example:

try {
  // code that may throw an error
} catch (err) {
  // error handling code
}
If there are no errors within the try block, the catch block is skipped, and the program continues executing after the try...catch statement. However, if an error occurs, the program jumps directly to the catch block, allowing you to handle the error appropriately. You can also include a finally block after the catch block to specify code that should be executed regardless of whether an error occurred or not.

In SQL (Transact-SQL): In SQL, the TRY...CATCH construct is used to handle errors within a block of code. The TRY block contains the code that may throw an error, and the CATCH block contains the error handling code. If an error occurs within the TRY block, the execution is immediately transferred to the CATCH block, allowing you to handle the error. The error object in SQL is not explicitly named, but you can reference it using the ERROR_MESSAGE() function to retrieve the error message. Here's an example:

BEGIN TRY
  -- code that may generate an error
END TRY
BEGIN CATCH
  -- error handling code
  SELECT ERROR_MESSAGE();
END CATCH
Within the CATCH block, you can perform actions such as logging the error, rolling back transactions, or returning error messages to the calling application. The TRY...CATCH construct in SQL can also be combined with other error handling mechanisms, such as RAISERROR or THROW statements, to customize the error handling behavior.

Overall, the try...catch statement allows you to handle and manage errors in a controlled manner, providing a way to gracefully recover from unexpected situations and take appropriate actions.

# What is the difference between a block element and an inline element?
- Block elements:
Respect left and right margins and padding.
Can have a width and height set.
Force a line break after the block element.
Acquire full width if width is not defined.


- Inline elements:
Do not respect top and bottom margins and padding.
Cannot have a width and height set.
Allow other elements to sit to their left and right.


- Inline-block elements:
Allow other elements to sit to their left and right.
Respect top and bottom margins and padding.
Respect height and width.
Behave like inline elements in terms of being on the same line as adjacent content.
Behave like block elements in terms of allowing width and height to be set.


# What is Ref?
- In the context of React, a "ref" is a feature provided by React to access the underlying DOM element or a React component instance. It allows you to interact with the DOM or access the methods and properties of a component directly. The concept of refs is used when you need to modify or interact with a child component without relying on props.

- To create a ref in React, you can use the React.createRef() function. This creates a ref object that can be attached to a React element using the ref attribute. For example:


# Generating a random number ?
// Returns a random integer from 0 to 9:
Math.floor(Math.random() * 10);


# Dates in JS 
- Year new Date().getFullYear() return year only
- new Date().getMonth() returns Month
- new Date().getDate() returns Date
- new Date().getHours return hours
- new Date().getMinutes return minutes
- new Date().getSeconds return Seconds

- new Date() returns Fri Jun 23 2023 14:19:36 GMT+0530 (India Standard Time)
- Date.now()  The Date.now() static method returns the number of milliseconds elapsed since the epoch, which is defined as the midnight at the beginning of January 1, 1970, UTC.


- To determine if a given date is before or after the current date, you can use different approaches depending on the programming language you are using. Here are some possible solutions:

JavaScript: In JavaScript, you can compare dates using the Date object and its methods. Here's an example:
const givenDate = new Date('2023-06-23');
const currentDate = new Date();

if (givenDate > currentDate) {
  console.log('Given date is after the current date');
} else if (givenDate < currentDate) {
  console.log('Given date is before the current date');
} else {
  console.log('Given date is the same as the current date');
}


# - What do mean by controlled and uncontrolled components?
- Controlled Components: A controlled component is a React component that handles the form elements and their data through the component's state. The component's state is used to store the current value of the form elements, and the component itself controls the changes to the form elements by updating its state. The form elements are rendered with the value attribute bound to the corresponding state property, and the changes to the form elements are handled through the onChange event.

Here's an example of a controlled component in React:
```
import React, { useState } from 'react';

function ControlledComponent() {
  const [name, setName] = useState('');

  const handleChange = (event) => {
    setName(event.target.value);
  };

  return (
    <input type="text" value={name} onChange={handleChange} />
  );
}
```
- Uncontrolled Components: An uncontrolled component is a React component where the form elements store their own state internally, and the component does not manage the form data through its state. Instead, you can access the form element's value using a ref to query the DOM when needed.
 ```
   import React, { useRef } from 'react';

function UncontrolledComponent() {
  const inputRef = useRef(null);

  const handleSubmit = (event) => {
    event.preventDefault();
    console.log(inputRef.current.value);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" ref={inputRef} />
      <button type="submit">Submit</button>
    </form>
  );
}
```

# Class Components vs Functional Components.
- Conclusion In conclusion, class components and functional components both have their use cases in React. Class components were the traditional way of handling state and lifecycle methods, but with the introduction of Hooks, functional components gained similar capabilities. Functional components offer a simpler syntax and can be more concise, while class components may be preferred by developers accustomed to object-oriented programming. Performance-wise, there is usually no significant difference between the two types of components. It's important to choose the approach that best suits your project requirements and personal coding style.

  # what is virtual DOM?
  - In summary, the Virtual DOM is a lightweight JavaScript representation of the actual DOM used in declarative web frameworks. It optimizes the process of updating the DOM by making changes to a virtual representation and then determining and applying the minimal set of changes needed to update the actual DOM.


# What is useMemo?

# what is short circuiting in JS ?
- Short-circuiting in JavaScript refers to the behavior of logical operators, specifically the OR (||) and AND (&&) operators, when evaluating expressions. When an expression involving these operators is evaluated, JavaScript will "short-circuit" and not evaluate the remaining operands if the final result can be determined based on the values of the previous operands.

- In the case of the OR operator (||), if the first operand is true, JavaScript will short-circuit and return true without evaluating the second operand. This is because if one operand is true, the entire expression is true. If the first operand is false, JavaScript will evaluate the second operand.

Here's an example:

true || false; // true
false || true; // true
true || true; // true
false || false; // false

# whats diffrence between forking a repo and cloning a repo? 
- To summarize, forking creates an independent copy of a repository under your account, allowing you to make changes without affecting the original repository. Cloning, on the other hand, creates a local copy of a repository on your machine, enabling you to work on the codebase and contribute changes back to the original repository.


# What are some of the important features of React?
- React is a popular JavaScript library for building user interfaces. It offers several important features that make it a preferred choice for many developers. Here are some of the important features of React:

- Virtual DOM: React uses a virtual DOM (Document Object Model) which is a lightweight copy of the actual DOM. This allows React to efficiently update only the necessary parts of the UI, resulting in improved performance compared to traditional DOM manipulation.
- Component-based architecture: React follows a component-based architecture, where the UI is divided into reusable components. Components encapsulate their own logic and can be easily reused throughout the application. This promotes code reusability and modularity, making it easier to maintain and scale the application.
- Unidirectional data flow: React follows a unidirectional data flow, also known as one-way data binding. This means that data flows from parent components to child components, and any changes in the child components are communicated back to the parent components through callbacks. This helps in maintaining a predictable state and makes it easier to debug and understand the application's behavior.
- JSX syntax: React uses JSX (JavaScript XML) syntax, which allows developers to write HTML-like code within JavaScript. JSX makes it easier to create and manipulate UI components, as it provides a familiar syntax for working with HTML elements and attributes.
- React Native: React can be used not only for web development but also for mobile app development through React Native. React Native allows developers to build native mobile apps using React components, providing a seamless development experience for both web and mobile platforms.
- Developer tools: React provides dedicated tools for easy debugging, such as the React Developer Tools extension for Chrome. These tools help developers inspect and debug React components, making the development process faster and more efficient.


# use Callback?
- One reason to use useCallback is to prevent a component from re-rendering unless its props have changed.
In this example, you might think that the Todos component will not re-render unless the todos change:
https://www.youtube.com/shorts/eCnplWBF8zs

- To fix this, we can use the useCallback hook to prevent the function from being recreated unless necessary.
Use the useCallback Hook to prevent the Todos component from re-rendering needlessly:

```
import { useState, useCallback } from "react";

import ReactDOM from "react-dom/client";

import Todos from "./Todos";

const App = () => {

  const [count, setCount] = useState(0);
  
  const [todos, setTodos] = useState([]);

  const increment = () => {
    setCount((c) => c + 1);
  };
  const addTodo = useCallback(() => {
  
    setTodos((t) => [...t, "New Todo"]);
    
  }, [todos]);

  return (
    <>
      <Todos todos={todos} addTodo={addTodo} />
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
      </div>
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```
```
- child component
- import { memo } from "react";

const Todos = ({ todos, addTodo }) => {
  console.log("child render");
  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => {
        return <p key={index}>{todo}</p>;
      })}
      <button onClick={addTodo}>Add Todo</button>
    </>
  );
};

export default memo(Todos);
```

# use Memo?
- The useMemo Hook can be used to keep expensive, resource intensive functions from needlessly running.
In this example, we have an expensive function that runs on every render.
When changing the count or adding a todo, you will notice a delay in execution.

- Think of memoization as caching a value so that it does not need to be recalculated.
- The useMemo Hook only runs when one of its dependencies update.
- The useMemo and useCallback Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function. You can learn more about useCallback in the useCallback chapter.

```
- import { useState, useMemo } from "react";
import ReactDOM from "react-dom/client";

const App = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState([]);
  const calculation = useMemo(() => expensiveCalculation(count), [count]);

  const increment = () => {
    setCount((c) => c + 1);
  };
  const addTodo = () => {
    setTodos((t) => [...t, "New Todo"]);
  };

  return (
    <div>
      <div>
        <h2>My Todos</h2>
        {todos.map((todo, index) => {
          return <p key={index}>{todo}</p>;
        })}
        <button onClick={addTodo}>Add Todo</button>
      </div>
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
        <h2>Expensive Calculation</h2>
        {calculation}
      </div>
    </div>
  );
};

const expensiveCalculation = (num) => {
  console.log("Calculating...");
  for (let i = 0; i < 1000000000; i++) {
    num += 1;
  }
  return num;
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

# useRef()
- The useRef Hook allows you to persist values between renders.
It can be used to store a mutable value that does not cause a re-render when updated.
It can be used to access a DOM element directly.

- If we tried to count how many times our application renders using the useState Hook, we would be caught in an infinite loop since this Hook itself causes a re-render.
To avoid this, we can use the useRef Hook.

- useRef() only returns one item. It returns an Object called current.
When we initialize useRef we set the initial value: useRef(0).
It's like doing this: const count = {current: 0}. We can access the count by using count.current.
Run this on your computer and try typing in the input to see the application render count increase.

```
import { useState, useEffect, useRef } from "react";
import ReactDOM from "react-dom/client";

function App() {
  const [inputValue, setInputValue] = useState("");
  const count = useRef(0);

  useEffect(() => {
    count.current = count.current + 1;
  });

  return (
    <>
      <input
        type="text"
        value={inputValue}
        onChange={(e) => setInputValue(e.target.value)}
      />
      <h1>Render Count: {count.current}</h1>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);

```

# useContext
- React Context is a way to manage state globally.
It can be used together with the useState Hook to share state between deeply nested components more easily than with useState alone.

```
import { useState, createContext, useContext } from "react";
import ReactDOM from "react-dom/client";

const UserContext = createContext();

function Component1() {
  const [user, setUser] = useState("Jesse Hall");

  return (
    <UserContext.Provider value={user}>
      <h1>{`Hello ${user}!`}</h1>
      <Component2 />
    </UserContext.Provider>
  );
}

function Component2() {
  return (
    <>
      <h1>Component 2</h1>
      <Component3 />
    </>
  );
}

function Component3() {
  return (
    <>
      <h1>Component 3</h1>
      <Component4 />
    </>
  );
}

function Component4() {
  return (
    <>
      <h1>Component 4</h1>
      <Component5 />
    </>
  );
}

function Component5() {
  const user = useContext(UserContext);

  return (
    <>
      <h1>Component 5</h1>
      <h2>{`Hello ${user} again!`}</h2>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Component1 />);
```

# what is babel ?
- Babel is a JavaScript compiler that is mainly used to convert ECMAScript 2015+ code into a backwards-compatible version of JavaScript for current and older browsers or environments babeljs.io. It is an essential tool in React development, as it allows developers to use the latest JavaScript features without worrying about browser compatibility. Babel can also transform JSX syntax, which is used in React components babeljs.io.

# what is ES6 ?
- ES6 stands for ECMAScript 6.
ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015.

# What is JSX?
- JSX stands for JavaScript XML.
- With JSX you can write expressions inside curly braces { }.
  ```
  const myElement = <h1>React is {5 + 5} times better with JSX</h1>;
  ```
  - Inserting a Large Block of HTML
```
    const myElement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
    );
```

- class = className 
- for = htmlFor

Conditions - if statements
 # React supports if statements, but not inside JSX.
```
function Goal(props) {
  const isGoal = props.isGoal;
  if (isGoal) {
    return <MadeGoal/>;
  }
  return <MissedGoal/>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Goal isGoal={false} />);
```
To be able to use conditional statements in JSX, you should put the if statements outside of the JSX, or you could use a ternary expression instead:

```
const x = 5;

const myElement = <h1>{(x) < 10 ? "Hello" : "Goodbye"}</h1>;
```
# what are props?
- React Props are like function arguments in JavaScript and attributes in HTML.
To send props into a component, use the same syntax as HTML attributes:
```
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <h2>I am a { prop.brand.name }!</h2>;
}

function Garage() {
  const carName = "Ford";
  return (
    <>
	    <h1>Who lives in my garage?</h1>
	    <Car brand={ name: "Ford", model: "Mustang" } />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
# Rendering array
- In React, you will render lists with some type of loop.
The JavaScript map() array method is generally the preferred method.

```
function Car(props) {
  return <li>I am a { props.brand }</li>;
}

function Garage() {
  const cars = [
    {id: 1, brand: 'Ford'},
    {id: 2, brand: 'BMW'},
    {id: 3, brand: 'Audi'}
  ];
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <ul>
        {cars.map((car) => <Car key={car.id} brand={car.brand} />)}
      </ul>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

# Routing in React

```
npm i -D react-router-dom

import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} />
          <Route path="blogs" element={<Blogs />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);

```
- We wrap our content first with <BrowserRouter>.
- Then we define our <Routes>. An application can have multiple <Routes>. Our basic example only uses one.
- <Route>s can be nested. The first <Route> has a path of / and renders the Layout component.
- The nested <Route>s inherit and add to the parent route. So the blogs path is combined with the parent and becomes /blogs.
- The Home component route does not have a path but has an index attribute. That specifies this route as the default route for the parent route, which is /.
- Setting the path to * will act as a catch-all for any undefined URLs. This is great for a 404 error page.


- The Layout component has <Outlet> and <Link> elements.
- The <Outlet> renders the current route selected.
- <Link> is used to set the URL and keep track of browsing history.
- Anytime we link to an internal path, we will use <Link> instead of <a href="">.
- The "layout route" is a shared component that inserts common content on all pages, such as a navigation menu.

```
import { Outlet, Link } from "react-router-dom";

const Layout = () => {
  return (
    <>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/blogs">Blogs</Link>
          </li>
          <li>
            <Link to="/contact">Contact</Link>
          </li>
        </ul>
      </nav>

      <Outlet />
    </>
  )
};

export default Layout;
```


# what is context api?
- same as useContext
- The Context API is a feature in React that allows you to share data with multiple components without having to pass data through props manually. It can be useful for scenarios like theming, user language, authentication, and more.

# what is getter and setter method in JS?
- In JavaScript, getter and setter methods are used to access and manipulate object properties, providing a convenient way to control how a certain field is initialized and provided to the user. This can help improve data quality and encapsulation in your code scaler.com.

A getter method is used to access the properties of an object, like this:
```
const student = {
  firstName: 'Monica',
  get getName() {
    return this.firstName;
  }
};

console.log(student.getName); // Monica
```
- A setter method is used to change the values of an object, like this:
```
const student = {
  firstName: 'Monica',
  set changeName(newName) {
    this.firstName = newName;
  }
};

console.log(student.firstName); // Monica
student.changeName = 'Sarah';
console.log(student.firstName); // Sarah
```
```
var obj = {
  n: 67,
  get id() {
      return 'The ID is: ' + this.n;
  },
  set id(val) {
      if (typeof val === 'number')
          this.n = val;
  }
}

console.log(obj.id); // "The ID is: 67"
obj.id = 893;
console.log(obj.id); // "The ID is: 893"
obj.id = 'hello';
console.log(obj.id); // "The ID is: 893"
```

# what is the value of this  in a call back function passed to a event listener?
- In a callback function passed to an event listener, this refers to the DOM element that triggered the event. This allows you to access properties and methods of the element directly within the callback function developer.mozilla.org.

Here's an example of using this in a callback function:
```
const button = document.querySelector('button');

function handleClick(event) {
  console.log('Button clicked!');
  console.log(this); // <button> element that triggered the event
}

button.addEventListener('click', handleClick);
```

# using drag and drop 
- use react-beautiful-dnd 
- and remove React strict mode form index.js
