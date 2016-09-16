# React

1. **Declarative**
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
Declarative views make your code more predictable and easier to debug.

2. **Component-Based**
Build encapsulated (dikemas) components that manage their own state (pernyataan), then compose them to make complex UIs.
Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.

3. **Learn Once, Write Anywhere**
We don't make assumptions about the rest of your technology stack, so you can develop new features in React without rewriting existing code.
React can also render on the server using Node and power mobile apps using **React Native**.

**A Stateful Component**

In addition to taking input data (accessed via **this.props**), a component can maintain internal state data (accessed via **this.state**). When a component's state data changes, the rendered markup will be updated by **re-invoking render()**.

**An Application**

Using **props** and **state**, we can put together a **small Todo application**. This example uses **state** to track the current list of items as well as the text that the user has entered. Although event handlers appear to be rendered inline, they will be collected and implemented using event delegation.






