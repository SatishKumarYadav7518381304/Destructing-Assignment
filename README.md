# Destructing-Assignment


Ques 1  Destructing Assignment

Ans     To count the occurrences of a specific element in an array, you can create a JavaScript function that iterates through the array and keeps a count of the occurrences. Here's an example of a function that counts occurrences:

function countOccurrences(arr, element) {
  let count = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === element) {
      count++;
    }
  }
  return count;
}

// Example usage:
const numbers = [1, 2, 3, 4, 2, 2, 5, 2, 6];
const targetNumber = 2;

const occurrences = countOccurrences(numbers, targetNumber);
console.log(`The number ${targetNumber} appears ${occurrences} times in the array.`);


In this code:

* The countOccurrences function takes an array arr and an element as input.

* It initializes a count variable to 0 to keep track of the occurrences.

* It then loops through the array, checking if each element is equal to the target element. If a match is found, it increments the count variable.

* After the loop, it returns the count variable, which represents the number of occurrences of the target element in the array.

In the example usage, we're counting how many times the number 2 appears in the numbers array. You can replace the numbers array and targetNumber with your own data to count occurrences of any element in an array.


Ques 2   Only unique items are allowed.

Ans   If you want to count the occurrences of unique items in an array (i.e., count how many times each unique element appears), you can use a slightly modified approach with an object to keep track of the counts for each unique element. Here's an example:

function countUniqueOccurrences(arr) {
  const counts = {};

  // Loop through the array and count unique occurrences
  for (const item of arr) {
    counts[item] = (counts[item] || 0) + 1;
  }

  // Convert the counts object into an array of objects with item and count properties
  const uniqueOccurrences = Object.keys(counts).map(item => ({
    item,
    count: counts[item]
  }));

  return uniqueOccurrences;
}

// Example usage:
const items = [1, 2, 3, 4, 2, 2, 5, 2, 6];

const uniqueOccurrences = countUniqueOccurrences(items);
console.log(uniqueOccurrences);


In this code:

* The countUniqueOccurrences function takes an array arr as input.

* It initializes an empty object counts to keep track of the counts of unique items.

* It then loops through the array and, for each element, increments the count in the counts object. This effectively counts the unique occurrences of each item.

Finally, it converts the counts object into an array of objects with item and count properties to represent the unique occurrences.

The uniqueOccurrences array will contain objects representing unique items and their respective counts. You can use this approach to count occurrences of unique items in an array while eliminating duplicates.


Ques  3    Swap the values.

Ans     To swap the values of two variables in JavaScript, you can use a temporary variable to store one of the values temporarily. Here's an example of how to swap two values:

  let a = 5;
let b = 10;

console.log("Before swapping:");
console.log("a =", a);
console.log("b =", b);

// Swap the values
let temp = a;
a = b;
b = temp;

console.log("After swapping:");
console.log("a =", a);
console.log("b =", b);

In this code:

* We have two variables, a and b, with initial values.

* To swap the values, we use a third variable, temp, to temporarily store the value of a.

* We then assign the value of b to a and finally assign the value of temp (which was originally a) to b.

* After this swapping process, the values of a and b have effectively swapped.

This code will output the following:

Before swapping:
a = 5
b = 10
After swapping:
a = 10
b = 5


Ques 4   Access random elements.

Ans    To access random elements from an array in JavaScript, you can generate a random index within the valid index range of the array and then use that index to access the corresponding element. Here's an example of how to access a random element from an array:

// Sample array
const fruits = ["apple", "banana", "cherry", "date", "elderberry", "fig", "grape"];

// Function to access a random element from the array
function getRandomElement(arr) {
  const randomIndex = Math.floor(Math.random() * arr.length);
  return arr[randomIndex];
}

// Example usage:
const randomFruit = getRandomElement(fruits);
console.log("Random fruit:", randomFruit);


In this code:

* We have an array named fruits containing various fruit names.

* The getRandomElement function takes an array arr as input and generates a random index within the range of valid indices in the array using Math.random().

* We use Math.floor() to ensure the index is a whole number.

* The function returns the element at the randomly generated index in the array.

* When we call getRandomElement(fruits), it returns a random fruit from the fruits array.

Each time you call getRandomElement(fruits), it will return a different random element from the array.

Ques 5. Min and max values.

Ans    To find the minimum and maximum values in an array of numbers in JavaScript, you can use the Math.min and Math.max functions, or you can implement custom functions to achieve the same result. Here's how you can do both:

Using Math.min and Math.max

const numbers = [5, 3, 9, 1, 7, 2, 8, 4, 6];

const minValue = Math.min(...numbers);
const maxValue = Math.max(...numbers);

console.log("Minimum value:", minValue);
console.log("Maximum value:", maxValue);


Using custom functions:

const numbers = [5, 3, 9, 1, 7, 2, 8, 4, 6];

function findMinValue(arr) {
  return arr.reduce((min, current) => (current < min ? current : min), arr[0]);
}

function findMaxValue(arr) {
  return arr.reduce((max, current) => (current > max ? current : max), arr[0]);
}

const minValue = findMinValue(numbers);
const maxValue = findMaxValue(numbers);

console.log("Minimum value:", minValue);
console.log("Maximum value:", maxValue);


Both approaches will give you the same result: the minimum and maximum values in the array. The first method is more concise and makes use of built-in functions, while the second method involves custom functions for finding the min and max values using the reduce method.




Ques 6 Nested Objects.

Ans   Nested objects in JavaScript allow you to create complex data structures where objects can contain other objects as properties. This hierarchical structure is useful for organizing and representing data in a meaningful way. Here's an example of how to work with nested objects:

// Creating a nested object
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
  address: {
    street: "123 Main St",
    city: "Anytown",
    state: "CA",
    postalCode: "12345"
  },
  contact: {
    email: "john.doe@example.com",
    phone: "555-123-4567"
  }
};

// Accessing nested properties
console.log("First Name:", person.firstName);
console.log("Street:", person.address.street);
console.log("Email:", person.contact.email);

// Modifying nested properties
person.age = 31;  // Update the age
person.address.city = "Newtown";  // Change the city name
person.contact.phone = "555-987-6543";  // Update the phone number

// Adding new properties to the nested objects
person.address.country = "USA";
person.contact.socialMedia = {
  facebook: "facebook.com/johndoe",
  twitter: "@johndoe"
};

// Deleting properties
delete person.address.postalCode;

console.log(person);

In this example:

* We create a nested object called person, which contains properties like firstName, lastName, age, address, and contact. The address and contact properties are themselves objects with their own nested properties.

* We access nested properties using dot notation (e.g., person.address.street) to retrieve values.

* We modify nested properties by directly assigning new values (e.g., person.age = 31).

* We can add new properties to the nested objects, such as country to the address object and socialMedia to the contact object.

* We can delete properties using the delete operator (e.g., delete person.address.postalCode).

Nested objects are a powerful way to organize and work with structured data, and they are commonly used in JavaScript to represent complex entities or configurations.






