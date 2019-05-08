# Callback Functions

Created: May 07, 2019 9:54 AM
Tags: Day 2,Week 3

A function that can be called as a parameter, or argument to another function.

Example: 

    const functionFeeder = function(callback) {
    	callback("Hello from the inside of Function Feeder.");
    }
    
    // Invocation
    functionFeeder(function(greeting) {
    	console.log(greeting);
    }

Example 2:

Example 3:

    // The callback function
    function sayHello(name) {
    	console.log(`Hello, ${name}`);
    }
    
    // The function that uses sayHello as an argument.
    function callSayHelloWithLars(callback) {
    	const innerName = "Lars";
    	callback(innerName);
    }
    
    // Invoking 
    callSayHelloWithLars(sayHello);

    const elements = ["Fire", "water", "wind", "earth"]
    
    // The function that uses the callback
    const newForEach = (list, callback) => {
    	for(let i = 0; i < list.length; i++) {
    	callback(list[i], i);
    	}
    };
    
    // Invoking newForEach
    newForEach(elements, (item, index) => {
    	console.log(item, index);
    });

Example 3.1: 

Example 4:

    const elements = ["fire", "water", "wind", "earth"]
    
    // The function that uses the callback
    const newForEach = (list, callback) => {
    	for(let i = 0; i < list.length; i++) {
    	callback(list[i], i);
    	}
    };
    
    // The callback
    const iterator = (item, index) => {
    	console.log(item, index);
    }
    
    // Invoking newForEach
    newForEach(elements, iterator);

    const elements = ["fire", "water", "wind", "earth"]
    
    function showFirst(array, callback) {
    	callback(array[0]);
    }
    
    // Invoking
    showFirst(elements, // This is the callback: 
    (firstItem) => {
    	console.log(firstItem);
    });