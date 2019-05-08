# Array Methods

Created: May 07, 2019 10:42 AM
Tags: Day 2,Week 3

`.map()` Returns a new array of elements. Calls back each element, and index, and then returns each. Typically used for manipulating or reshaping data. ***Does not alter the array it was called on.***

Example: 

    const mappedCityStates = data.map((state) => {
    	return {"city": state.city, "state": state.state};
    });

`.filter()` Returns a new array of elements. Every time the function loops it will call back each element, and index and then returns each. The callback that it takes runs a truth test. If true, returns the elements, where false elements are ignored entirely. ***Does not alter the array it was called on.***

Example:

    const filterLargeStates = data.filter((state) => {
    	return state.population >= 65000;
    });

`.reduce()` Returns a new array. Takes a callback which is a reducer function. Reducer function takes a previous value and a next value known as an *accumulator* and *currentValue* respectively. Used for manipulating or reshaping data into a single value.

Example: 

    const reuceStatePopulations = data.reduce((total, state) => {
    	return total += state.population;
    }, 0); 

`.forEach()` loops through an array of items, and displays a given output.

Example:

    var array1 = ['a', 'b', 'c'];
    
    array1.forEach(function(element) {
      console.log(element);
    });
    
    // expected output: "a"
    // expected output: "b"
    // expected output: "c"
    

Advanced use of `.filter + callbacks`:

    const hasDupes = ["Pencil", "Pencil", "Notebook" "yo-yo", "Gum"]
    
    function removeDuplicates(array, cb) {
      // removeDuplicates removes all duplicate values from the given array.
      // Pass the duplicate free array to the callback function.
      // Do not mutate the original array.
    
      cb(array.filter(function(value, index, array) {
        return array.indexOf(value) === index;
      }));
    }
    removeDuplicates(hasDupes, function(noDupes) {
      console.log(noDupes);
    });

- Array Method Cheat Sheet

    [Arrayzing - The JavaScript array cheatsheet](https://gist.github.com/ourmaninamsterdam/1be9a5590c9cf4a0ab42)