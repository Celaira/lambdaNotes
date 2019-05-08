# Closures

Created: May 07, 2019 9:34 AM
Tags: Day 2,Week 3

The ability for variables within a `function scope` to reach outward to get information, but never inward. Meaning that, while functions can look to the variables outside of them for information, nothing can reach *in* to a function to get information.

`Functional Scope` - When a new function is declared, a new scope is created.

Example:

    const foo = "bar";
    function returnFoo() {
    	return foo;
    }
    returnfoo();

Example 2:

    const lastName = "Bond";
    function greet() {
    	const firstName = "James";
    	alert(`The name's ${lastName}, ${firstName} ${lastName}.`);
    }