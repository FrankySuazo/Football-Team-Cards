# Football-Team-Cards
In this project, is a build of a set of football team cards and learn about nested objects, object destructuring, default parameters, event listeners, and switch statements.  Will only explain the JavaScript section


Start by accessing the id called "team" from the HTML document and storing it in a const variable called teamName.

Remember, you can use the getElementById method for this.

Next, access the id called "sport" from the HTML document and store it in a const variable called typeOfSport. Below that variable, assign the id of year to a const variable called worldCupYear.

Next, access the id called "head-coach" from the HTML document and store it in a const variable called headCoach. Below that variable, assign the id of "player-cards" to a const variable called playerCards.

Create one more const variable called playersDropdownList and assign it the id of "players" using the getElementById method.

Now it is time to build out the data structure that will hold all of the information for your football team.

Below the variables that's just created, create a new const variable called myFavoriteFootballTeam and assign it an empty object.

Inside the myFavoriteFootballTeam object, add a new property with a key named team and a string value of "Argentina".

Below the team property, add a new property with a key named sport and a string value of "Football".

Below the sport property, add a new property with a key named year and a number value of 1986.

Below the year property, add a new property with a key named isWorldCupWinner and a boolean value set to true.

Below the isWorldCupWinner property, add a new key called headCoach with a value of an empty object. Inside that object, add a property with a key of coachName and a string value of "Carlos Bilardo". Below that property, add another key called matches with a number value of 7.

Below the headCoach property, create a new property with a key named players with the value of an empty array.

Inside that players array, create a new object with some properties

The next step is to ensure that object can't be modify by adding or removing any properties. We are going to use a method called Object.freeze(obj) which will freeze this object and prevent any changes being made to it.

Used the Object.freeze() method to freeze the myFavoriteFootballTeam object.

The next step is to access the key called sport from the myFavoriteFootballTeam object and assign it to a new const variable called sport.

Below the sport variable, access the key called team from the myFavoriteFootballTeam object and assign it to a new const variable called team.

Rewrite the two lines of code below using the new destructuring syntax

Next, add the year and players to your destructuring assignment.

Now you need to access the coachName value from the myFavoriteFootballTeam.headCoach object using the destructuring syntax.

Below your destructuring assignments, assign the sport variable to typeOfSport.textContent.

Next, assign the team variable to teamName.textContent.

Assign the year variable to worldCupYear.textContent.

Below that, assign the coachName variable to headCoach.textContent.

You should now see all of that information displayed on the screen below Team stats.

Now will start building out the function that will show player cards based on the selections made by the user in the Filter Teammates dropdown menu.

Start by creating an empty arrow function called setPlayerCards. Do not need to add a parameter because that will be taken care of in the next step.

Add a new parameter to your setPlayerCards function called arr and assign it a default value of players.

Inside the setPlayerCards function, start by adding the map method to arr that will take in an empty callback function. Then, use the addition assignment += operator to assign the new array to playerCards.innerHTML.

Remember that the innerHTML property gets, or in this case, sets the HTML markup for the playerCards element.

Inside the parameter list in the callback function for the map method, unpack all 5 object properties from objects in arr using object destructuring.

Inside the template literals, add an empty div with a class of "player-card".

Inside the div, add an h2 element which contains the name parameter. Since you are working with template literals, you will need to use an embedded expression for the name parameter

The next step would be to display the word (Captain) next to the player if they are listed as a captain for the team.

Right next to the ${name} expression, add a new embedded expression. Inside that expression, use a ternary operator to check if isCaptain is true. If so, return (Captain) otherwise return an empty string.

Below the h2 element, add a paragraph element with the text Position: and an embedded expression that contains the position parameter.

Below the paragraph element, add another paragraph element with the text Number: and an embedded expression that contains the number parameter.

Below your existing paragraph elements, add another paragraph element with the text Nickname: .

Next to the Nickname: text, add an embedded expression that will show the player's nickname if they have one.

To remove the commas between each player-card so it does not show up on screen, chain the .join() method to the .map() method. Pass an empty string as the argument for the .join() method.

The next step is to create a function that will detect when a user makes a selection from the playersDropdownList.

Used the .addEventListener() method on playersDropdownList. Inside the event listener, pass in a "change" event type and an empty callback function.

For the callback function, pass in e as a parameter.

e represents an object which contains the information for that event.

Inside the callback function, add a console.log with the value of e.target.value.

The next step would be to reset the content for the playerCards element.

Inside the callback function, access the innerHTML property of the playerCards element and assign it a value of an empty string.

The next step would be to add a switch statement which will check for the user's selection from the player dropdown menu and filter out cards based on the player's positions.

Add a switch statement and use e.target.value for the expression.

If the user selects Nicknames from the dropdown menu you will want to filter out player cards that have a nickname.

Start by adding a case clause for "nickname" inside your switch statement.

Call the setPlayerCards function with an argument of players.filter().

Inside the filter method, add a callback function with a parameter called player and implicitly return player.nickname is not null.

Below your setPlayerCards call, add a break statement.

Inside that case, call the setPlayerCards function with an argument of players.filter().

Inside the filter() method, add a callback function with a parameter of player that will check if player.position equals "forward".

Lastly, add a break statement below the setPlayerCards function call.

Add a new case for "midfielder" that checks if player.position equals "midfielder" following the same pattern from the previous step.

Add a new case for "defender" that checks if player.position equals "defender" following the same pattern as the previous step.

Add a new case for "goalkeeper" that checks if player.position equals "goalkeeper" following the same pattern as the previous step.

For the default clause, call the setPlayerCards function without any arguments passed in.

