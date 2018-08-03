# Various React Concepts, Best Practices, and Conventions

## Coding Conventions
* native HTML elements begin with lowercase
* React class / components begin with uppercase
    - ie.
    ```
    <Component   />
    <div> </div>
    ```

## Concepts
* props
    - are immutable
    - they are passed from the parent, and owned by the parent
* state 
    - is mutable
    - private to the component
    - changed by calling this.setState()
    - when the state updates, the component re-renders itself
* render()
    - returns a tree of React components, that eventually will render to HTML
    - render methods are written declaratively as functions of this.props and this.state
    - the framework guarantees the UI is always consistent with the inputs
* JSX 
    - even the html native elements in jsx, are actually instantiations of React components (which eventually get rendered as HTML)
* Creating a React Component
    - can extend a component class
    - or, pass some methods in an object to React.createClass()
* setState vs. assigning value to state 
    - assigning a value simply assigns the value, and does not rerender (skips react lifecycle)
    - setState, updates the values of state and rerenders 
    - for the most part, you should always use setState, except when in setting intial state values in a constructor
    - __NOTE: setState is asynchronous__
        + you must exit the function you are calling it from, in order for react to be able to update state 
        + e.g. if you call setState, then right after access state, state likely will not show the updated value
    - NOTES on this topic
        + http://stackoverflow.com/questions/34961853/what-will-happen-if-i-use-setstate-function-in-constructor-of-a-class-in-react
        + https://facebook.github.io/react/docs/component-api.html#setstate
        + http://stackoverflow.com/questions/35867038/what-the-difference-of-this-state-and-this-setstate-in-reactjs
* reading values of state 
    - be careful when trying to access state, setting state = to a local var will do so via reference
        + e.g. `const formErrors = this.state.formErrors;`
        + any change to formErrors will change this.state.formErrors!
        + if you need a copy of the values, consider this manner
            * const formErrors = { ...this.state.formErrors }
     
## Design Patterns
### Presentational Components
* normal react components, primary purpose is for presentation 
    - typically does not collect data 
    - best practice is to be a pure function
* typically functional stateless components
    - unless need to use local state, or lifecycle methods, then convert to react class
### Container Components
* provide data and behavior to presentational components
### State (Flux / Redux)
* Redux: Three Principles
    - Single Source of Truth (state stored in an object tree within a single store)
    - State is read-only (must emit an action to change state)
    - Changes are made with pure functions (using pure reducer functions)

## Best Practices / Coding Patterns
* [Binding methods of classes, to preserve `this` context.](https://medium.com/@rjun07a/binding-callbacks-in-react-components-9133c0b396c6)
