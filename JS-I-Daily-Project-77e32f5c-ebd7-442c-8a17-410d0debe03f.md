# JS-I Daily Project

Created: May 07, 2019 5:31 PM
Tags: Day 1,Week 3

`objects.js`:

    // Let's get some practice writing a few objects for a new group of interns at a small business.
    
    // ==== Challenge 1: Writing Objects ==== 
    // HR needs some information on the new interns put into a database.  Given an id, email, first name, and gender. Create an object for each person in the company list:
    
    // 1,mmelloy0@psu.edu,Mitzi,F
    // 2,kdiben1@tinypic.com,Kennan,M
    // 3,kmummery2@wikimedia.org,Keven,M
    // 4,gmartinson3@illinois.edu,Gannie,M
    // 5,adaine5@samsung.com,Antonietta,F
    
    // Example format of an intern object: 1,examples@you.edu,Example,F
    const example = {
      "id": 0,
      "name": "Example",
      "email": "examples@you.edu",
      "gender": "F"
    }
    
    // Write your intern objects here:
    const intern1 = {
      "id": 1,
      "name": "Mitzi",
      "email": "mmelloy0@psu.edu",
      "gender": "F"
    }
    
    const intern2 = {
      "id": 2,
      "name": "Kennan",
      "email": "kdiben1@tinypic.com",
      "gender": "M",
      speak: function () {
        return `Hi, my name is ${this.name}`;
      }
    }
    
    const intern3 = {
      "id": 3,
      "name": "Keven",
      "email": "kmummery2@wikimedia.org",
      "gender": "M"
    }
    
    const intern4 = {
      "id": 4,
      "name": "Gannie",
      "email": "gmartinson3@illinois.edu",
      "gender": "M"
    }
    
    const intern5 = {
      "id": 5,
      "name": "Antonietta",
      "email": "adaine5@samsung.com",
      "gender": "F",
      multiplyNums: function(num1, num2) {
        return num1 * num2;
      }
    }
    
    // ==== Challenge 2: Reading Object Data ==== 
    // Once your objects are created, log out the following requests from HR into the console:
    
    // Mitzi's name
    console.log(intern1.name);
    
    // Kennan's ID
    console.log(intern2.id);
    
    // Keven's email
    console.log(intern3.email);
    
    // Gannie's name
    console.log(intern4.name);
    
    // Antonietta's Gender
    console.log(intern5.gender);
    
    
    // ==== Challenge 3: Object Methods ==== 
    // Give Kennan the ability to say "Hello, my name is Kennan!" Use the console.log provided as a hint.
    
    console.log(intern2.speak());
    // Antonietta loves math, give her the ability to multiply two numbers together and return the product. Use the console.log provided as a hint.
    console.log(intern5.multiplyNums(3,4));
    
    // === Great work! === Head over to the the arrays.js file or take a look at the stretch challenge
    
    // ==== Stretch Challenge: Nested Objects and the this keyword ==== 
    
    // 1. Create a parent object with properties for name and age.  Make the name Susan and the age 70.
    // 2. Nest a child object in the parent object with name and age as well.  The name will be George and the age will be 50.
    // 3. Nest a grandchild object in the child object with properties for name and age.  The name will be Sam and the age will be 30
    // 4. Give each of the objects the ability to speak their names using the this keyword.
    
    const parent = {
      "name": "Susan",
      "age": 70,
      speak: function() {
        console.log(`My name is ${this.name}`);
      },
      child: {
        "name": "George",
        "age": 50,
        speak: function() {
          console.log(`My name is ${this.name}`);
        },
        grandchild: {
          "name": "Sam",
          "age": 30,
          speak: function() {
            console.log(`My name is ${this.name}`);
          }
        }
      }
    }
    
    // Log the parent object's name
    console.log(parent.name);
    // Log the child's age
    console.log(parent["child"].age);
    // Log the name and age of the grandchild
    console.log(parent.child.grandchild["name"], parent.child.grandchild["age"]);
    // Have the parent speak
    parent.speak();
    // Have the child speak
    parent["child"].speak();
    // Have the grandchild speak
    parent["child"]["grandchild"].speak();

`arrays.js`:

    // To help us use arrays with real world problems we are going to simulate a used car dealer that has 50 cars in their inventory.
    
    // The car dealer has all of their inventory housed in the array seen below.  Scroll down past the data to find out how you can help the car dealer.
    
    let inventory = [{"id":1,"car_make":"Lincoln","car_model":"Navigator","car_year":2009},
    {"id":2,"car_make":"Mazda","car_model":"Miata MX-5","car_year":2001},
    {"id":3,"car_make":"Land Rover","car_model":"Defender Ice Edition","car_year":2010},
    {"id":4,"car_make":"Honda","car_model":"Accord","car_year":1983},
    {"id":5,"car_make":"Mitsubishi","car_model":"Galant","car_year":1990},
    {"id":6,"car_make":"Honda","car_model":"Accord","car_year":1995},
    {"id":7,"car_make":"Smart","car_model":"Fortwo","car_year":2009},
    {"id":8,"car_make":"Audi","car_model":"4000CS Quattro","car_year":1987},
    {"id":9,"car_make":"Ford","car_model":"Windstar","car_year":1996},
    {"id":10,"car_make":"Mercedes-Benz","car_model":"E-Class","car_year":2000},
    {"id":11,"car_make":"Infiniti","car_model":"G35","car_year":2004},
    {"id":12,"car_make":"Lotus","car_model":"Esprit","car_year":2004},
    {"id":13,"car_make":"Chevrolet","car_model":"Cavalier","car_year":1997},
    {"id":14,"car_make":"Dodge","car_model":"Ram Van 1500","car_year":1999},
    {"id":15,"car_make":"Dodge","car_model":"Intrepid","car_year":2000},
    {"id":16,"car_make":"Mitsubishi","car_model":"Montero Sport","car_year":2001},
    {"id":17,"car_make":"Buick","car_model":"Skylark","car_year":1987},
    {"id":18,"car_make":"Geo","car_model":"Prizm","car_year":1995},
    {"id":19,"car_make":"Oldsmobile","car_model":"Bravada","car_year":1994},
    {"id":20,"car_make":"Mazda","car_model":"Familia","car_year":1985},
    {"id":21,"car_make":"Chevrolet","car_model":"Express 1500","car_year":2003},
    {"id":22,"car_make":"Jeep","car_model":"Wrangler","car_year":1997},
    {"id":23,"car_make":"Eagle","car_model":"Talon","car_year":1992},
    {"id":24,"car_make":"Toyota","car_model":"MR2","car_year":2003},
    {"id":25,"car_make":"BMW","car_model":"525","car_year":2005},
    {"id":26,"car_make":"Cadillac","car_model":"Escalade","car_year":2005},
    {"id":27,"car_make":"Infiniti","car_model":"Q","car_year":2000},
    {"id":28,"car_make":"Suzuki","car_model":"Aerio","car_year":2005},
    {"id":29,"car_make":"Mercury","car_model":"Topaz","car_year":1993},
    {"id":30,"car_make":"BMW","car_model":"6 Series","car_year":2010},
    {"id":31,"car_make":"Pontiac","car_model":"GTO","car_year":1964},
    {"id":32,"car_make":"Dodge","car_model":"Ram Van 3500","car_year":1999},
    {"id":33,"car_make":"Jeep","car_model":"Wrangler","car_year":2011},
    {"id":34,"car_make":"Ford","car_model":"Escort","car_year":1991},
    {"id":35,"car_make":"Chrysler","car_model":"300M","car_year":2000},
    {"id":36,"car_make":"Volvo","car_model":"XC70","car_year":2003},
    {"id":37,"car_make":"Oldsmobile","car_model":"LSS","car_year":1997},
    {"id":38,"car_make":"Toyota","car_model":"Camry","car_year":1992},
    {"id":39,"car_make":"Ford","car_model":"Econoline E250","car_year":1998},
    {"id":40,"car_make":"Lotus","car_model":"Evora","car_year":2012},
    {"id":41,"car_make":"Ford","car_model":"Mustang","car_year":1965},
    {"id":42,"car_make":"GMC","car_model":"Yukon","car_year":1996},
    {"id":43,"car_make":"Mercedes-Benz","car_model":"R-Class","car_year":2009},
    {"id":44,"car_make":"Audi","car_model":"Q7","car_year":2012},
    {"id":45,"car_make":"Audi","car_model":"TT","car_year":2008},
    {"id":46,"car_make":"Oldsmobile","car_model":"Ciera","car_year":1995},
    {"id":47,"car_make":"Volkswagen","car_model":"Jetta","car_year":2007},
    {"id":48,"car_make":"Dodge","car_model":"Magnum","car_year":2008},
    {"id":49,"car_make":"Chrysler","car_model":"Sebring","car_year":1996},
    {"id":50,"car_make":"Lincoln","car_model":"Town Car","car_year":1999}];
    
    
    // Example for loop:
    
    // arr = [1,2,3,4];
    // for (let i = 0; i < arr.length; i++) {
    //     arr[i]; // 1,2,3,4
    // }
    
    // ==== Challenge 1 ====
    // The dealer can't recall the information for a car with an id of 33 on his lot. Help the dealer find out which car has an id of 33 by logging the car's year, make, and model in the console log provided to you below:
    
    
    console.log(`Car 33 is a ${inventory[inventory.length - 18].car_year} ${inventory[inventory.length - 18]["car_make"]} ${inventory[inventory.length - 18]["car_model"]}` );
    
    // ==== Challenge 2 ====
    // The dealer needs the information on the last car in their inventory.  What is the make and model of the last car in the inventory?  Log the make and model into the console.
    let lastCar = inventory[inventory.length - 1];
    console.log(`${lastCar["car_make"]}, ${lastCar["car_model"]}`);
    
    // ==== Challenge 3 ====
    // The marketing team wants the car models listed alphabetically on the website. Sort all the car model names into alphabetical order and log the results in the console
    let carModels = inventory.sort(function(a, b) {
        if(a.car_model < b.car_model) {
            return -1;
        }
        return 1;
    });
    
    for(let i = 0; i < carModels.length; i++) {
        console.log(carModels[i].car_model);
    }
    console.log(carModels);
    
    // ==== Challenge 4 ====
    // The accounting team needs all the years from every car on the lot. Create a new array from the dealer data containing only the car years and log the result in the console.
    let carYears = inventory.map(car => {
        return car.car_year;
    })
    console.log(carYears);
    
    // ==== Challenge 5 ====
    // The car lot manager needs to find out how many cars are older than the year 2000. Using the carYears array you just created, find out how many cars were made before the year 2000 by populating the array oldCars and logging it's length.
    let oldCars = inventory.filter(obj => {
        if(obj.car_year < 2000) {
            return true;
        };
    });
    console.log(oldCars.length); 
    
    // ==== Challenge 6 ====
    // A buyer is interested in seeing only BMW and Audi cars within the inventory.  Return an array that only contains BMW and Audi cars.  Once you have populated the BMWAndAudi array, use JSON.stringify() to show the results of the array in the console.
    let BMWAndAudi = inventory.filter(obj => {
        if(obj.car_make === "Audi" || obj.car_make === "BMW"){
        return true;
    }
    });
    console.log(JSON.stringify(BMWAndAudi));

`function-conversion.js`:

    // Take the commented ES5 syntax and convert it to ES6 arrow Syntax
    
    // let myFunction = function () {
    // console.log("Function was invoked!");
    // };
    // myFunction();
    
    let myFunction = () => {
        console.log("Function was invoked!");
    }
    
    myFunction();
    
    // let anotherFunction = function (param) {
    //   return param;
    // };
    // anotherFunction("Example");
    
    let anotherFunction = (param) => {
        return param;
    }
    
    anotherFunction("Example")
    
    // let add = function (param1, param2) {
    //   return param1 + param2;
    // };
    // add(1,2);
    
    let add = (param1, param2) => {
        return param1 + param2;
    }
    
    add(1, 2);
    
    // let subtract = function (param1, param2) {
    //   return param1 - param2;
    // };
    // subtract(1,2);
    
    let subtract = (param1, param2) => {
        return param1 - param2;
    }
    
    subtract(1, 2);
    
    // Stretch
    
    // exampleArray = [1,2,3,4];
    // const triple = exampleArray.map(function (num) {
    //   return num * 3;
    // });
    // console.log(triple);
    
    const exampleArray = [1, 2, 3, 4];
    
    const triple = exampleArray.map(
        (num) => {
            return num * 3;
        }
    );
    
    console.log(triple);