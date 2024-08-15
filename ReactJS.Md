# In recent reactjs coding round, this was asked. Can you solve this ?

Implement a todo list component in React. User can add todos, mark todos as completed and filter todos

1. Each todo object should have a text property and a completed property.
2. Display the list of todos.Each todo should be displayed as a checkbox with the todo text as its label. The checkbox should be checked if the todo is completed.
3. The component should have a input field and a button for adding new todos. When the button is clicked, a new todo should be added to the list with the input fied's value as its text and completed set to false.
4. When a todo checkbox is clicked, the completed property of that todo should be toggled.
5. The component should have buttons for filtering the list of todos. There should be three filters. "ALL","ACTIVE","COMPLETED". "ALL" should show all the todos, "ACTIVE" should show todos where completed is false. "COMPLETED" should show only the todos where completed is true.

---

# How do you measure the performance of a webapplication ?

---

In recent reactjs machine coding round, this was asked. Can you solve this ?

1.get the data from below url

https://datausa.io/api/data?drilldowns=Nation&measures=Population

2. Display a table which should contain years and population from this api
3. Add a input where user can search year or population appy debouncing here.

4.Add a reset button which will reset the data in table to initial data.

5. Add delete option in each row which should delete respective row when clicked.

---

In recent reactjs interview, this machine coding problem was asked. Can you solve this ?

1. The UI should look like shown in the image above with 7 boxes shaped in C shape.
2. On clicking the box, its color changes to green.
3. When all boxes are green, they should again go back to the previous color yellow, one by one, by a 1-second delay, in the same order as they were clicked.

---

# What is Lazy loading in React ?

Lazy loading is a technique used in React to improve performance and reduce the initial load time of web applications. It allows you to split your code into smaller chunks, and load them on demand only when they are needed. This can significantly reduce the amount of JavaScript that needs to be loaded initially, which can improve the page load speed and user experience.

To implement lazy loading in React, you can use the "React.lazy" function. This function allows you to load a component lazily, i.e., only when it is needed.

---

What is useCallback in React ?

usecallback hook will return the memoized version of the callback function that only changes if one of the dependencies have been changed.

It is useful for optimizing performance by preventing unnecessary renders.

---

# React Memo

This function returns memoized return value of the component.

it renders the component and returns the result of component & also memoizes (stores) its result.

it doesn't re-render the component; instead, it returns the memoized result of component.

it renders the component and returns the result of component & also memoizes (stores) its result (same as first render).

# useCallback

This hook returns memoized function to prevent unnecessary re-renders of child components with React.memo().

<pre class="prettyprint linenums prettyprinted" role="presentation"><ol class="linenums"><li class="L0"><p><span class="kwd">let</span><span class="pln"> myFunction </span><span class="pun">=</span><span class="pln"></span><span class="pun">(</span><span class="pln"></span><span class="pun">)</span><span class="pln"></span><span class="pun">=></span></p></li><li class="L1" data-node-id="20240815123823-86jl6sc"><p><span class="pun">{</span></p></li><li class="L2"><p><span class="pun">};</span></p></li></ol></pre>

<pre class="prettyprint linenums prettyprinted" role="presentation"><ol class="linenums"><li class="L0"><p><span class="kwd">let</span><span class="pln"> myFunction </span><span class="pun">=</span><span class="pln"> useCallback</span><span class="pun">(</span></p></li><li class="L1" data-node-id="20240815123823-8f9gz67"><p><span class="pun">(</span><span class="pln"></span><span class="pun">)</span><span class="pln"></span><span class="pun">=></span><span class="pln"></span><span class="pun">{</span><span class="pln"></span><span class="pun">},</span></p></li><li class="L2"><p><span class="pun">[</span><span class="pln"> dependencies </span><span class="pun">]</span></p></li><li class="L3" data-node-id="20240815123823-krd0l55"><p><span class="pun">);</span></p></li></ol></pre>

**When you invoke useCallback with a function inside the component:**

**First render**

it creates a function and returns the same function & also memoizes (stores) the same function.

**Subsequent renders with same values of dependencies**

it creates a function but returns the same memoized function;

**Subsequent renders with some changes in values of dependencies.**

it creates a function and returns the same function & also memoizes (stores) the same function.

# When to use useCallback

When the child component is invoked with React.memo() and also the parent component is passing a callback function to the child component.

or

When your useEffect hook's dependencies array has a callback function.

Ex: useEffect(…, [ callback ] );

**Note: **Avoid using useCallback when your component is smaller.

# useRef

This hook return reference to DOM element object of an element

we can call DOM method using this reference

```
let myRef = useRef(initialValue)

<element ref={myRef}}>

myRef.current.SomeDomMethod())
```


What are controlled and uncontrolled components in Reactjs
