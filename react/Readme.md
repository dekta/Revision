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
                <script src="https://content.codecademy.com/courses/React/react-18-course-bundle.min.js"></script>
            <script src="/index.compiled.js"></script>
            </body>
            </html>

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
        ```javascript
            function LoginMsg(props) {
            if (props.password === 'a-tough-password') {
                return <h2>Sign In Successful.</h2>
            } else {
                return <h2>Sign In Failed..</h2>
            }
            }
        ```
#### Pass an Event Handler as a prop
    ```javascript
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
    ```javascript
        function Example({text='This is default text'}) {
            return <h1>{text}</h1>
        }




