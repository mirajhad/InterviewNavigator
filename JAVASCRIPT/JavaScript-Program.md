1. Program to find longest word in a given sentence ?
2. How to check whether a string is palindrome or not ?
3. Write a program to remove duplicates from an array ?
4. Program to find Reverse of a string without using built-in method ?
5. Find the max count of consecutive 1’s in an array ?
6. Find the factorial of given number ?
7. Given 2 arrays that are sorted [0,3,4,31] and [4,6,30]. Merge them and sort [0,3,4,4,6,30,31] ?
8. Create a function which will accepts two arrays arr1 and arr2. The function should return true if every value in arr1 has its corresponding value squared in array2. The frequency of values must be same.
9. Given two strings. Find if one string can be formed by rearranging the letters of other string.
10. Write logic to get unique objects from below array ?
    I/P: [{name: "sai"},{name:"Nang"},{name: "sai"},{name:"Nang"},{name: "111111"}];
    O/P: [{name: "sai"},{name:"Nang"}{name: "111111"}
11. Write a JavaScript program to find the maximum number in an array.
12. Write a JavaScript function that takes an array of numbers and returns a new array with only the even numbers.
13. Write a JavaScript function to check if a given number is prime.
14. Write a JavaScript program to find the largest element in a nested array.
    [[3, 4, 58], [709, 8, 9, [10, 11]], [111, 2]]
15. Write a JavaScript function that returns the Fibonacci sequence up to a given number of terms.
16. Given a string, write a javascript function to count the occurrences of each character in the string.
17. Write a javascript function that sorts an array of numbers in ascending order.
18. Write a javascript function that sorts an array of numbers in descending order.
19. Write a javascript function that reverses the order of words in a sentence without using the built-in reverse() method.
20. Implement a javascript function that flattens a nested array into a single-dimensional array.
21. Write a function which converts string input into an object
    ("a.b.c", "someValue");
    {a: {b: {c: "someValue"}}}


Duplicate Element

var arr=[1,2,3,3,3];

let unique=[];

for(let i=0;i<arr.length;i++){

if(unique.indexOf(arr[i])==-1){

    unique.push(arr[i])

}

}

console.log(unique);
