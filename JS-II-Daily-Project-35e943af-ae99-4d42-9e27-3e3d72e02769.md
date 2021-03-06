# JS-II Daily Project

Created: May 07, 2019 4:41 PM
Tags: Day 2,Week 3

`callbacks.js`:

    // Create a higher order function and invoke the callback function to test your work. You have been provided an example of a problem and a solution to see how this works with our items array.  Study both the problem and the solution to figure out the rest of the problems.
    
    const items = ['Pencil', 'Notebook', 'yo-yo', 'Gum'];
    
    /* 
    
      //Given this problem: 
      
      function firstItem(arr, cb) {
        // firstItem passes the first item of the given array to the callback function.
      }
    
      // Potential Solution:
    
      // Higher order function using "cb" as the call back
      function firstItem(arr, cb) {
        return cb(arr[0]);
      }
    
      // Function invocation 
      firstItem(items, function(first) {
        console.log(first)
      });
    
    */
    
    
    function getLength(arr, cb) {
      // getLength passes the length of the array into the callback.
      cb(arr.length);
    }
    
    getLength(items, (length) => { 
      console.log(length);
    });
    
    function last(arr, cb) {
      // last passes the last item of the array into the callback.
      cb(arr[arr.length - 1]);
    }
    
    last(items, (lastItem) => {
      console.log(lastItem);
    });
    
    function sumNums(x, y, cb) {
      // sumNums adds two numbers (x, y) and passes the result to the callback.
      let result = x + y;
      cb(result);
    }
    
    sumNums(5, 45, (answer) => {
      console.log(answer);
    })
    
    function multiplyNums(x, y, cb) {
      // multiplyNums multiplies two numbers and passes the result to the callback.
      let result = x * y;
      cb(result);
    }
    
    multiplyNums(45, 103, (answer) => {
      console.log(answer)
    });
    
    function contains(item, list, cb) {
      // contains checks if an item is present inside of the given array/list.
      // Pass true to the callback if it is, otherwise pass false.
      list.filter(function(obj) {
        if(obj === item) {
          cb(true)
        } else {
          cb(false)
        }
      });
    }
    
    contains("Pencil", items, (answer) => {
      console.log(answer);
    })
    
    /* STRETCH PROBLEM */
    
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
      console.log(noDupes)
    });

`closure.js`:

    // ==== Challenge 1: Write your own closure ====
    // Write a simple closure of your own creation.  Keep it simple!
    const smoldev = "me"
    
    function whoIsSmolDev() {
      console.log(smoldev);
    }
    
    whoIsSmolDev()
    
    /* STRETCH PROBLEMS, Do not attempt until you have completed all previous tasks for today's project files */
    
    
    // ==== Challenge 2: Create a counter function ====
    const counter = () => {
      // Return a function that when invoked increments and returns a counter variable.
      let count = 0;
      
      return function() {
        count++;
        return count;
      }
    };
    // Example usage: const newCounter = counter();
    // newCounter(); // 1
    // newCounter(); // 2
    
    const newCounter = counter();
    
    console.log(newCounter());
    console.log(newCounter());
    console.log(newCounter());
    console.log(newCounter());
    
    // ==== Challenge 3: Create a counter function with an object that can increment and decrement ====
    
    const counterFactory = () => {
      // Return an object that has two methods called `increment` and `decrement`.
      // `increment` should increment a counter variable in closure scope and return it.
      // `decrement` should decrement the counter variable and return it.
      let count = 0;
      return {
        increment: function() {
          count++;
          return count;
        },
        
        decrement: function() {
          count--;
          return count;
        }
      }
    };
    
    const newCounterFactory = counterFactory();
    
    console.log(newCounterFactory.increment()); 
    // console.log(counterFactory(increment())); // says increment is undefined
    console.log(newCounterFactory.increment());
    console.log(newCounterFactory.increment());

`array-methods.js`:

    // A local community center is holding a fund raising 5k fun run and has invited 50 small businesses to make a small donation on their behalf for some much needed updates to their facilities.  Each business has assigned a representative to attend the event along with a small donation.
    
    // Scroll to the bottom of the list to use some advanced array methods to help the event director gather some information from the businesses.
    
    const runners = [{"id":1,"first_name":"Charmain","last_name":"Seiler","email":"cseiler0@wired.com","shirt_size":"2XL","company_name":"Divanoodle","donation":75},{"id":2,"first_name":"Whitaker","last_name":"Ierland","email":"wierland1@angelfire.com","shirt_size":"2XL","company_name":"Wordtune","donation":148},{"id":3,"first_name":"Julieta","last_name":"McCloid","email":"jmccloid2@yahoo.com","shirt_size":"S","company_name":"Riffpedia","donation":171},{"id":4,"first_name":"Martynne","last_name":"Paye","email":"mpaye3@sciencedaily.com","shirt_size":"XL","company_name":"Wordware","donation":288},{"id":5,"first_name":"Gussy","last_name":"Raraty","email":"graraty4@ucoz.ru","shirt_size":"L","company_name":"Oozz","donation":291},{"id":6,"first_name":"Yule","last_name":"Tommasetti","email":"ytommasetti5@state.gov","shirt_size":"S","company_name":"Yodo","donation":27},{"id":7,"first_name":"Kathie","last_name":"Majury","email":"kmajury6@guardian.co.uk","shirt_size":"3XL","company_name":"Zoomcast","donation":261},{"id":8,"first_name":"Tanner","last_name":"Branton","email":"tbranton7@tmall.com","shirt_size":"2XL","company_name":"Realmix","donation":28},{"id":9,"first_name":"Sarina","last_name":"Lasham","email":"slasham8@toplist.cz","shirt_size":"XL","company_name":"Gigashots","donation":110},{"id":10,"first_name":"Bertie","last_name":"Lonergan","email":"blonergan9@issuu.com","shirt_size":"3XL","company_name":"Skinte","donation":62},{"id":11,"first_name":"Trevor","last_name":"Studd","email":"tstudda@networkadvertising.org","shirt_size":"S","company_name":"Cogidoo","donation":76},{"id":12,"first_name":"Malachi","last_name":"Okeshott","email":"mokeshottb@chron.com","shirt_size":"M","company_name":"DabZ","donation":91},{"id":13,"first_name":"Berget","last_name":"Logsdail","email":"blogsdailc@wix.com","shirt_size":"M","company_name":"Mymm","donation":9},{"id":14,"first_name":"Loise","last_name":"Rivlin","email":"lrivlind@behance.net","shirt_size":"2XL","company_name":"Linktype","donation":204},{"id":15,"first_name":"Christan","last_name":"Kendall","email":"ckendalle@example.com","shirt_size":"XS","company_name":"Skinix","donation":252},{"id":16,"first_name":"Kayla","last_name":"Whitwam","email":"kwhitwamf@deliciousdays.com","shirt_size":"2XL","company_name":"Oyope","donation":147},{"id":17,"first_name":"Heddie","last_name":"Heningam","email":"hheningamg@tripadvisor.com","shirt_size":"L","company_name":"Skinix","donation":172},{"id":18,"first_name":"Mace","last_name":"Ballinger","email":"mballingerh@a8.net","shirt_size":"S","company_name":"Nlounge","donation":266},{"id":19,"first_name":"Nola","last_name":"Abberley","email":"nabberleyi@jalbum.net","shirt_size":"XL","company_name":"Photospace","donation":148},{"id":20,"first_name":"Nadine","last_name":"Tresler","email":"ntreslerj@marketwatch.com","shirt_size":"3XL","company_name":"Wikido","donation":292},{"id":21,"first_name":"Ulrikaumeko","last_name":"Vuittet","email":"uvuittetk@gov.uk","shirt_size":"S","company_name":"Skinte","donation":102},{"id":22,"first_name":"Saunder","last_name":"Spennock","email":"sspennockl@icq.com","shirt_size":"3XL","company_name":"Kwimbee","donation":213},{"id":23,"first_name":"Carmel","last_name":"Woffinden","email":"cwoffindenm@wikispaces.com","shirt_size":"S","company_name":"Rooxo","donation":137},{"id":24,"first_name":"Marielle","last_name":"Kimmel","email":"mkimmeln@jimdo.com","shirt_size":"M","company_name":"Livetube","donation":96},{"id":25,"first_name":"Brucie","last_name":"Burris","email":"bburriso@slate.com","shirt_size":"2XL","company_name":"Wordtune","donation":128},{"id":26,"first_name":"Juan","last_name":"Berzon","email":"jberzonp@soup.io","shirt_size":"3XL","company_name":"Einti","donation":234},{"id":27,"first_name":"Sacha","last_name":"Olsen","email":"solsenq@reverbnation.com","shirt_size":"2XL","company_name":"Viva","donation":190},{"id":28,"first_name":"Jamey","last_name":"O'Nolan","email":"jonolanr@samsung.com","shirt_size":"XL","company_name":"Skinix","donation":31},{"id":29,"first_name":"Morrie","last_name":"Rainard","email":"mrainards@yale.edu","shirt_size":"XS","company_name":"Podcat","donation":52},{"id":30,"first_name":"Fidel","last_name":"Roskelly","email":"froskellyt@ibm.com","shirt_size":"XS","company_name":"Avavee","donation":5},{"id":31,"first_name":"Toni","last_name":"MacSweeney","email":"tmacsweeneyu@parallels.com","shirt_size":"M","company_name":"Jaloo","donation":82},{"id":32,"first_name":"Jessey","last_name":"Walhedd","email":"jwalheddv@slashdot.org","shirt_size":"L","company_name":"Trilia","donation":5},{"id":33,"first_name":"Karola","last_name":"Piper","email":"kpiperw@ucsd.edu","shirt_size":"3XL","company_name":"Yombu","donation":110},{"id":34,"first_name":"Marley","last_name":"Mitchenson","email":"mmitchensonx@webeden.co.uk","shirt_size":"M","company_name":"Zoonoodle","donation":97},{"id":35,"first_name":"Marrilee","last_name":"Thrasher","email":"mthrashery@opensource.org","shirt_size":"XL","company_name":"Bluejam","donation":17},{"id":36,"first_name":"Tye","last_name":"Manie","email":"tmaniez@netscape.com","shirt_size":"L","company_name":"Kanoodle","donation":30},{"id":37,"first_name":"Charleen","last_name":"Sheering","email":"csheering10@mit.edu","shirt_size":"3XL","company_name":"Jatri","donation":262},{"id":38,"first_name":"Valma","last_name":"Eynaud","email":"veynaud11@archive.org","shirt_size":"XS","company_name":"Jaxbean","donation":212},{"id":39,"first_name":"Dollie","last_name":"McDarmid","email":"dmcdarmid12@tinyurl.com","shirt_size":"S","company_name":"Kayveo","donation":74},{"id":40,"first_name":"Minna","last_name":"Hymas","email":"mhymas13@cornell.edu","shirt_size":"XS","company_name":"Vimbo","donation":101},{"id":41,"first_name":"Jsandye","last_name":"Frend","email":"jfrend14@ca.gov","shirt_size":"XS","company_name":"Latz","donation":156},{"id":42,"first_name":"Yevette","last_name":"Hacket","email":"yhacket15@wp.com","shirt_size":"XL","company_name":"Lazzy","donation":291},{"id":43,"first_name":"Hank","last_name":"Zebedee","email":"hzebedee16@ezinearticles.com","shirt_size":"L","company_name":"Gigashots","donation":241},{"id":44,"first_name":"Jodie","last_name":"Stawell","email":"jstawell17@yale.edu","shirt_size":"S","company_name":"Jaxspan","donation":262},{"id":45,"first_name":"Falito","last_name":"Karsh","email":"fkarsh18@pcworld.com","shirt_size":"S","company_name":"Mycat","donation":239},{"id":46,"first_name":"Reginauld","last_name":"Purselowe","email":"rpurselowe19@thetimes.co.uk","shirt_size":"L","company_name":"Jabbersphere","donation":11},{"id":47,"first_name":"Vida","last_name":"Tydd","email":"vtydd1a@dropbox.com","shirt_size":"S","company_name":"Quaxo","donation":55},{"id":48,"first_name":"Anderea","last_name":"MacGiolla Pheadair","email":"amacgiollapheadair1b@xing.com","shirt_size":"2XL","company_name":"Kwimbee","donation":214},{"id":49,"first_name":"Bel","last_name":"Alway","email":"balway1c@ow.ly","shirt_size":"S","company_name":"Voolia","donation":107},{"id":50,"first_name":"Shell","last_name":"Baine","email":"sbaine1d@intel.com","shirt_size":"M","company_name":"Gabtype","donation":171}];
    
    // ==== Challenge 1: Use .forEach() ====
    // The event director needs both the first and last names of each runner for their running bibs.  Combine both the first and last names into a new array called fullName. 
    let fullName = runners.forEach(function(name) {    
    	console.log(`${name.first_name} ${name.last_name}`);
    });
    
    console.log(fullName);
    
    // ==== Challenge 2: Use .map() ====
    // The event director needs to have all the runner's first names converted to uppercase because the director BECAME DRUNK WITH POWER. Convert each first name into all caps and log the result
    let allCaps = runners.map(function(name) {    
    	return name.first_name.toUpperCase();
    });
    
    console.log(allCaps); 
    
    // ==== Challenge 3: Use .filter() ====
    // The large shirts won't be available for the event due to an ordering issue.  Get a list of runners with large sized shirts so they can choose a different size. Return an array named largeShirts that contains information about the runners that have a shirt size of L and log the result
    let largeShirts = runners.filter(function(large) {
        if(large.shirt_size === "L") {
            console.log(`Runners with large size shirts: ${large.first_name} ${large.last_name} \n email: ${large.email}`);
        }
    });
    
    console.log(largeShirts);
    
    // ==== Challenge 4: Use .reduce() ====
    // The donations need to be tallied up and reported for tax purposes. Add up all the donations into a ticketPriceTotal array and log the result
    
    let ticketPriceTotal = runners.reduce(function(total, donations) {    
    	return total += donations.donation;
    }, 0);
    
    console.log(ticketPriceTotal);
    
    // ==== Challenge 5: Be Creative ====
    // Now that you have used .forEach(), .map(), .filter(), and .reduce().  I want you to think of potential problems you could solve given the data set and the 5k fun run theme.  Try to create and then solve 3 unique problems using one or many of the array methods listed above.
    
    // Problem 1
    
    // display runner 43's first and last name
    
    let runnerName = runners.filter((name) => {    
    	if(name.id === 43) {        
    		console.log(`${name.last_name.toUpperCase()}, ${name.first_name}`);    
    	}
    });
    
    console.log(runnerName);
    
    // Problem 2
    
    // display all last names in uppercase
    
    let lastCaps = runners.map(function(name) {
        return name.last_name.toUpperCase();
    });
    
    console.log(lastCaps);
    
    // Problem 3
    // filter donations that are less than 100 then add them together.

    let smallDonations = runners.filter(function(donate) {    
    	if(donate.donation < 100) {        
    		return true;    
    	}
    });
    
    let totalSmallDonations = smallDonations.reduce(function(total, donate) { 
    	return total += donate.donation;
    }, 0);
    
    console.log(totalSmallDonations);