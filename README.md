# Build-a-Bike-Rental-Shop
- [x] The first thing you need to do is start the terminal. Do that by clicking the "hamburger" menu at the top left of the screen, going to the "terminal" section, and clicking "new terminal". Once you open a new one, type echo hello terminal into the terminal and press enter.
- [x] You are going to build a bike rental shop. It will have a database, and a bash script to interact with the database. Use the terminal to connect to PostgreSQL by entering psql --username=freecodecamp --dbname=postgres.
- [x] List the databases with \l to see what databases are here.
- [x] You need your own database for the bike shop. Create a new database named bikes.
- [x] List databases again to make sure your database got created.
- [x] There it is. Connect to it so you can start building the structure of your bike shop database.
- [x] Your database needs three tables. One for your bike inventory, one for your customers, and one for the bikes that are rented out. Create a table named bikes in your database for the inventory.
- [x] Display the tables to make sure your table got created.
- [x] The table will have a few columns for bike information. First, is a unique ID column. Add a column to the bikes table named bike_id. Give it a type of SERIAL and make it a PRIMARY KEY.
- [x] Use the display command to view the details of the bikes table.
- [x] The first column is set. Add a column named type for the type of bike. Make it a VARCHAR(50) and give it a constraint of NOT NULL.
- [x] Display the details of the bikes table again.
- [x] The first two columns look good. Add a column named size to the bikes table that is an INT and has the NOT NULL constraint. This will be for the size of each bike.
- [x] Add another column to the table named available. Make it a boolean and has a constraint of NOT NULL. Also, give it a default value of TRUE. This will be set to false when someone rents out a bike.
- [x] Display the details of the bikes table again so you can make sure it's how you want it.
- [x] That table is done for now. Create another table named customers. It will store a name and phone number for each customer that rents a bike.
- [x] Add a customer_id column to your new table that is a type of SERIAL and make it a PRIMARY KEY.
- [x] Display the details of the customers table so you can make sure your new column is there.
- [x] There it is. Add a column named phone for customers' phone numbers. Make it a varying character that has a maximum length of 15 characters. Also, make sure it can't be null, and that it has to be unique.
- [x] Add the last column. Call it name and make it a VARCHAR(40) that can't be null.
- [x] Display the details of the customers table.
- [x] That table is finished. Lastly, you need a table to store which bikes are rented and who has rented them. Create a new table named rentals.
- [x] Add a rental_id column to your new table. Make it automatically increment with SERIAL and make it the primary key for this table.
- [x] Display the details of the rentals table.
- [x] Next, you need a column for the customer who is renting a bike. Add a column named customer_id. This will have an id of a customer from the customers table. Make the column an INT and NOT NULL to start.
- [x] Make the column you just added a foreign key that references the customer_id column from the customers table. Here's an example of how you can do that:
  ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column);
- [x] Display the details of the rentals table to make sure your key is set.
- [x] That foreign key is set. You need another column so you know what bike a customer is renting. Add a column named bike_id and make it an INT and NOT NULL.
- [x] Make that column a foreign key that references the bike_id column from the bikes table so you know what bike the id is for.
- [x] Display the details of the rentals table so you can make sure the key is correct.
- [x] Moving along. You want to know when a customer rents a bike, and when it gets returned. Add a column to your rentals table named date_rented that's a type of DATE. Make sure the entry can't be null, and give it a default value of NOW().
- [x] Display the details of the rentals table again.
- [x] It looks good. Lastly, you need a column for when a customer returns a bike. Add a column named date_returned that's a type of DATE.
- [x] View the details of the table again.
- [x] The tables are all finished. Display all the tables so you can see what you ended up with.
- [x] You have nine bikes in your inventory. Add the first one to your bikes table. It has a type of Mountain and a size of 27. Make sure to put your VARCHAR values in single quotes. The bike_id and available columns should be filled in automatically, so you don't need to worry about those.
- [x] View all the columns in your bikes table with SELECT.
- [x] Looks like it's all working, the bike_id and available columns were filled in automatically. Insert another bike. Give it a type of Mountain and a size of 28.
- [x] Add another Mountain bike to your inventory. Make it a 29-inch bike.
- [x] Add a 27-inch Road bike to the table.
- [x] Use SELECT to view all the data in the bikes table again.
- [x] Add the two bikes to your inventory, they are 28 and 29-inch Road bikes. Try to add them both with one command.
- [x] There's three more bikes. Add 19, 20, and 21-inch BMX bikes to your table. Try to add them with one command.
- [x] View all the data in your bikes table.
- [x] Your current inventory is all added. For the rest of the project, I recommend leaving that terminal open and connected, and that you should "split" the terminal so you have a second one to use for bash commands. Do that by clicking the "hamburger" menu at the top left of the window, going to the "terminal" section, and clicking "split terminal". After you have opened it, use the touch command to create a file named bike-shop.sh in the project folder.
- [x] This file will be the program for your bike rental shop. Open the file and add a "shebang" at the top so it uses bash when it's executed. If you don't remember, it looks like this: #!/bin/bash.
- [x] In the file, use echo with the -e flag to print ~~~~~ Bike Rental Shop ~~~~~ with a new line at the beginning and end.
- [x] Use the terminal (not the psql one) and the chmod command to make your file executable. Add the +x flag and bike-shop.sh to the command to do that.
- [x] Type ./bike-shop.sh in the terminal to run your script.
- [x] 😄 In the script, create an empty function named MAIN_MENU. This will have a few options to enter when the script runs to rent or return a bike.
- [x] In your function, echo the text How may I help you? so that there's a greeting when you go to the menu.
- [x] Call your MAIN_MENU at the bottom of the file so the function runs when you start the script.
- [x] Run the file in the terminal again so you can see what it is outputting.
- [x] It's coming along. Add another echo command in the function below the other one. Make it output text that looks like this:
  1. Rent a bike
  2. Return a bike
  3. Exit
  Note that there's an empty line at the start.
- [x] Run the file to make sure it worked.
- [x] You have some options displaying. Next, you need to get input from whoever is using the program. Use the read command to read input into a variable called MAIN_MENU_SELECTION below the options.
- [x] When an option gets entered, you need to take a user to one of those other menus. Add an empty RENT_MENU function below the MAIN_MENU function.
- [x] For the time being, just echo Rent Menu in the function so you can see if it's working.
- [x] Add an empty RETURN_MENU function below the RENT_MENU function for when a user enters the option to return a bike.
- [x] Use echo to print Return Menu in the function you just added. You will change these later.
- [x] Add an empty EXIT function below the RETURN_MENU function for when a user wants to exit the program.
- [x] This one probably doesn't need a placeholder message. In the EXIT function, use echo to print Thank you for stopping in. with a new line at the beginning and end of the message.
- [x] When a user enters an option at the main menu, you want to take them to the appropriate sub-menu. You can use a case statement for this. Here's an example:
  ```
  case EXPRESSION in
    PATTERN) STATEMENTS ;;
    PATTERN) STATEMENTS ;;
    PATTERN) STATEMENTS ;;
    *) STATEMENTS ;;
  esac
  ```
  The expression you want is the $MAIN_MENU_SELECTION variable. You are expecting it to be a 1, 2, or 3 for your various menus. Add a case statement that takes users to their corresponding menus. The * is for when anything else is entered. Take users to the MAIN_MENU when the variable isn't a 1, 2, or 3.
- [x] Run the script a few times and try out the different menus. Be sure to enter something other than one of the options to go to the main menu.
- [x] Add an argument to where you call MAIN_MENU in the case statement. It should be Please enter a valid option.. The next step will adjust the function so the message is printed when a user enters an invalid option.
- [x] At the top of the MAIN_MENU function, add an if condition that checks if there's an argument ($1) passed to the function. If there is, print the message with a new line in front of it.
- [x] Run the script and enter an invalid option to see the message. Exit the program when you are done.
- [x] Looks good. Delete the echo "Rent Menu" from the RENT_MENU function so you can start adding the ability to rent a bike from the database.
- [x] In the RENT_MENU function, add three single line comments; get available bikes, if no bikes available, and send to main menu, in that order.
- [x] To get the bikes available, you need to query the database from your script. Below the "shebang", add a PSQL variable that looks like this: PSQL="psql -X --username=freecodecamp --dbname=bikes --tuples-only -c". You will then be able to use it to query the database like this: $($PSQL "<query_here>").
- [x] Below the get available bikes comment. Create an AVAILABLE_BIKES variable that gets the bike_id, type, and size columns from the bikes table for the bikes that are available. Order the results by their bike_id column. Here's an example: AVAILABLE_BIKES=$($PSQL "<query_here>").
- [x] Below the new variable, use echo to print it. Place it in double quotes so it prints any new lines.
- [x] Run your script and go to the rent menu to see if the available bikes are being printed.
- [x] Awesome. In the psql prompt, set the available column to false for all the bikes so you can see what it prints when there's no bikes available.
- [x] Run your script and go to the rent menu to see the output.
- [x] So if there's no bike available, the variable will be empty. In the script, below the if no bikes available comment, add an if condition that checks if the variable is empty. Use -z to check if it's empty. Place the send to main menu comment in its STATEMENTS area.
- [x] Below the comment in the if you just added. Send users to the main menu and give them the message, Sorry, we don't have any bikes available right now.
- [x] Run the script and go to the rent menu to see the message. When you are done, exit the program.
- [x] If no bikes are available, you will get that message. Add an else to the if condition for when there is bikes available. In it, add four single line comments; display available bikes, ask for bike to rent, if input is not a number, and send to main menu.
- [x] Below the display available bikes comment you just added, use echo to print Here are the bikes we have available: with a new line in front of the message.
- [x] Move the echo command that prints all the available bikes below the message you just added.
- [x] In the psql prompt, set all the bikes, except for the BMX bikes, back to true so you can see a list of bikes to rent.
- [x] Run the script and go to the rent menu to see the list of bikes available.
- [x] Instead of directly printing the list, pipe the output into a while loop that reads each line. Here's how that looks:
  ```
  echo "$AVAILABLE_BIKES" | while read <VAR_1> <VAR_2> <VAR_3> <VAR_4> <VAR_5>
  do
    <STATEMENTS>
  done
  ```
  It will read the first line of your AVAILABLE_BIKES variable into the five variables. Each variable being the next word in the line. Read each line into variables, BIKE_ID BAR TYPE BAR SIZE. In the <STATEMENTS> area, use echo to print the BIKE_ID, TYPE, and SIZE variables, in that order.
- [x] Run the script and go to the rent menu again to see if it's working.
- [x] It's working 😄 Adjust the echo command that prints the bike info so that the first line printed would look like this: 1) 27" Mountain Bike. The rest would look the same, but with their bike info. Make sure to escape any characters you need to.
- [x] Run the script and go to the rent menu again to see what it looks like now.
- [x] That's better. Below the ask for bike to rent comment, print Which one would you like to rent? with a new line in front of it.
- [x] Just below that, add a command to read input into a variable named BIKE_ID_TO_RENT.
- [x] Next, you want to find out how to test if the user input is a number. In the terminal, enter [[ a =~ [0-9] ]]; echo $? to see if a is a number. The conditional expression will run, and echo $? will print the exit code of it (the last command).
- [x] It printed 1 for false. Meaning that a did not match the pattern [0-9], or a did not contain a number from 0-9. Enter the same commands, but check if a1 matches the pattern.
- [x] That printed 0 for true. a1 does contain a number from 0-9. Enter the same command, but change the pattern to ^[0-9]$. The ^ signifies the start of the pattern, and $ means the end. So the input will have to start, contain a number 0-9, and end.
- [x] 1 for false. a1 does not match the pattern. Using the same syntax, check if 1 matches the pattern.
- [x] 1 does match the pattern. It starts, contains a number, and ends. Check if 11 matches the same pattern.
- [x] That did not match because the pattern only allows a single number. Add a + after the [0-9] to allow any strings that start, contain one or more numbers, and end.
- [x] So that pattern will match any positive integers. You want to check if the input is not a number. Add ! in front of the comparison of the previous command to do that.
- [x] Back in your script, below the if input is not a number comment, add an if condition that checks if the input is not a number using the method you just practiced. Add the send to main menu comment in the then area of the if.
- [x] If the $BIKE_ID_TO_RENT variable is not a number, add the code to send users to the main menu with the message, That is not a valid bike number.
- [x] Run the script, go to the rent menu, and enter something that isn't a number to make sure it is working. When you are done, exit the program.
- [x] Add an else area for when the input is a number. Add these three single line comments in it; get bike availability, if not available, send to main menu.
- [x] Below the get bike availability comment you just added, create a BIKE_AVAILABILITY variable. Set it equal to a query that gets the available column from the bikes table for the input. Also, make sure to only get the row if it is available.
- [x] Right below the variable you just created, use echo to print it so you can see what it looks like.
- [x] Run the script a few times, go to the rent menu, enter a bike that is available and one that isn't.
- [x] The variable will be t or empty. Below the if not available comment, add an if condition that checks if it's empty. Put the send to main menu comment in its statements area.
- [x] In the if condition you just added, send users to the main menu with the message That bike is not available. if they input a number that isn't available.
- [x] Remove the line where you print the BIKE_AVAILABILITY variable. You don't need it anymore.
- [x] Run the script and go to the rent menu, enter a bike that isn't available to make sure it's working. When you are done, exit the program.
- [x] In the psql prompt, set all the bikes availability back to true.
- [x] In your script, add an else for when a bike is available. Add these four comments in the else area get customer info, if customer doesn't exist, get new customer name, and insert new customer.
- [x] As the comments say, you need to get the customer info and find out if they are an existing customer. Below the get customer info comment, print What's your phone number? with a new line
