In recent reactjs coding round, this was asked. Can you solve this ?

Implement a todo list component in React. User can add todos, mark todos as completed and filter todos

1. Each todo object should have a text property and a completed property.
2. Display the list of todos.Each todo should be displayed as a checkbox with the todo text as its label. The checkbox should be checked if the todo is completed.
3. The component should have a input field and a button for adding new todos. When the button is clicked, a new todo should be added to the list with the input fied's value as its text and completed set to false.
4. When a todo checkbox is clicked, the completed property of that todo should be toggled.
5. The component should have buttons for filtering the list of todos. There should be three filters. "ALL","ACTIVE","COMPLETED". "ALL" should show all the todos, "ACTIVE" should show todos where completed is false. "COMPLETED" should show only the todos where completed is true.

---

How do you measure the performance of a webapplication ?

---

In recent reactjs machine coding round, this was asked. Can you solve this ?

1. Create a react component that displays a timer with initial value 0.
2. There should be two buttons one to start/stop, and other to reset timer.
3. Clicking on start will start timer from 0 and increase timer value by 1 for every second and button text should change to "stop".
4. Clicking on stop will pause the timer and change button text to "start".
5. Now click on start then timer should continue from paused value.
6. Clicking on reset will reset the timer to initial value 0.

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

What is Lazy loading in React ?

Lazy loading is a technique used in React to improve performance and reduce the initial load time of web applications. It allows you to split your code into smaller chunks, and load them on demand only when they are needed. This can significantly reduce the amount of JavaScript that needs to be loaded initially, which can improve the page load speed and user experience.

To implement lazy loading in React, you can use the "React.lazy" function. This function allows you to load a component lazily, i.e., only when it is needed.

---

What is useCallback in React ?

usecallback hook will return the memoized version of the callback function that only changes if one of the dependencies have been changed.

It is useful for optimizing performance by preventing unnecessary renders.

---

What is useMemo ?

useMemo is used to memoize the value. means it caches the result of a function and returns the cached value until one of the dependencies has changed.

It is used to optimize the extensive computations. so that they are not recalculated on every render.

const memoizedValue = useMemo(()=>{

 return computeExtensiveValue(a,b)

},[a,b]);

---

What are controlled and uncontrolled components in Reactjs
