# fCC Javascript Calorie Counter
 Learn form validation/accepting user input through regular expression, template literals and addEventListener().

 Notes taken from this project:

- To access an HTML element with a given id name, you can use the getElementById() method.

- In programming, it is standard practice to prefix a variable with is or has to indicate that the variable is a boolean.

- The split() method splits a string into an array of substrings, and returns the new array. You can pass in an optional separator which tells the method where each split should happen.
- For example, passing an empty string into the split method will split the string into an array of individual characters.
const str = 'Hello World';
const strArray = str.split('');
// ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d"]

Use a for loop to iterate through each character in your strArray array.
    for (let i = 0; i < strArray.length; i++)

- You will need to check if the array ["+", "-", " "] does not include the current character. You can use a combination of the includes() method and the ! operator to do this.
- The .includes() method returns true if the array contains the character, and false if not. The logical NOT operator (!) will return the opposite of the value of the .includes() method.
- Here is an example checking if the current character is not in the vowels array. If it is not, that current character is pushed into the consonantArray:
const inputString = "Hello World";
const charArray = inputString.split('');
const consonantArray = [];

for (let i = 0; i < charArray.length; i++) {
  if (!['a', 'e', 'i', 'o', 'u'].includes(charArray[i])) {
    consonantArray.push(charArray[i]);
  }
}

- While looping through the string works, creating a new array is inefficient for memory and runtime performance. Instead, you can use Regular Expressions (referred to as "regex") to match specific characters.
- In regex, shorthand character classes allow you to match specific characters without having to write those characters in your pattern. Shorthand character classes are preceded with a backslash (\). The character class \s will match any whitespace character.
- To tell the pattern to match each of these characters individually, you need to turn them into a character class. This is done by wrapping the characters you want to match in brackets.
- Regex can also take specific flags to alter the pattern matching behavior. Flags are added after the closing /. The g flag, which stands for "global", will tell the pattern to continue looking after it has found a match.
- The e in a number input can also be an uppercase E. Regex has a flag for this, however – the i flag, which stands for "insensitive".
- The + modifier in a regex allows you to match a pattern that occurs one or more times. 
- There is a shorthand character class to match any digit: \d.

- Strings have a .match() method, which takes a regex argument. .match() will return an array of match results – containing either the first match, or all matches if the global flag is used.

- Strings have a .replace() method which allows you to replace characters in the string with another string. .replace takes two arguments. The first is the character sequence to replace – this can either be a string or a regex pattern. The second is the string to replace that sequence with. For example, this would replace all instances of l with 1:
"hello".replace(/l/g, "1");

- In HTML, number inputs allow for exponential notation (such as 1e10). You need to filter those out.

- You can use the value property to get the value of the selected option.

- Template literals allow you to interpolate variables directly within a string. Template literals are denoted with backticks ``, as opposed to single or double quotes.

- Variables can be passed in to a template literal by surrounding the variable with ${} – the value of the variable will be inserted into the string.

- You will want to number the entries a user adds. To get all of the number inputs, you can use the querySelectorAll() method.
- The querySelectorAll() method returns a NodeList of all the elements that match the selector. 
- A NodeList is an array-like object, so you can access the elements using bracket notation.
- Each entry will have a text input for the entry's name, and a number input for the calories. To get a count of the number of entries, you can query by text inputs. Note that you cannot query by number inputs, as you have an extra number input for the user's calorie budget.

- In the Role Playing Game project, you learned how to set a button's behavior by editing its onclick property. You can also edit an element's behavior by adding an event listener.
- The addEventListener method takes two arguments. The first is the event to listen to. (Ex. 'click') The second is the callback function, or the function that runs when the event is triggered.

- The insertAdjacentHtml method takes two arguments. The first argument is a string that specifies the position of the inserted element. The second argument is a string containing the HTML to be inserted.

- The list parameter is going to be the result of a query selector, which will return a NodeList. A NodeList is a list of elements like an array. It contains the elements that match the query selector. You will need to loop through these elements in the list.

- In previous steps, you learned how to loop through an array using a for loop. You can also use a for...of loop to loop through an array and a NodeList.
- A for...of loop is used to iterate over elements in an iterable object like an array. The variable declared in the loop represents the current element being iterated over.

- In JavaScript, values can either be truthy or falsy. A value is truthy if it evaluates to true when converted to a Boolean. A value is falsy if it evaluates to false when converted to a Boolean. null is an example of a falsy value.

- In programming, null is meant to represent the absence of a value.

- Remember that return ends the execution of a function.

- The Number constructor is a function that converts a value to a number. If the value cannot be converted, it returns NaN which stands for "Not a Number".

- You will be attaching this function to the submit event of the form. The submit event is triggered when the form is submitted. The default action of the submit event is to reload the page. You need to prevent this default action using the preventDefault() method of your e parameter.

- getElementById, which returns an Element, not a NodeList.
- A NodeList is an array-like, which means you can iterate through it and it shares some common methods with an array. For your getCaloriesFromInputs function, an array will work for the argument just as well as a NodeList does.

- Math.abs() is a built-in JavaScript method that will return the absolute value of a number.

- The Array object has a .from() method that accepts an array-like and returns an array. This is helpful when you want access to more robust array methods.

- The difference between innerText and innerHTML is that innerText will not render HTML elements, but will display the tags and content as raw text.