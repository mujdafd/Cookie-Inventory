# Cookie-Inventory
This JavaFX application is used to keep track of a cookie inventory. This project includes the 2 classes, 
1 enumeration, UI elements, and error handlings and exceptions.


The Cookies Enum 
This enumeration contains constants for each cookie flavour and is written in the cookies.jar file. Every 
flavour is assigned a name (displayed on the UI), a unqiue ID number, and a price.

The CookieInventoryItem Class
This class models a single record in the cookies.txt file. A CookieInventoryItem has a data member for the 
cookie flavour ID and the quantity of cookies currently available.

The CookieInventoryFile Class
This class models the collection of records (modeled by CookieInventoryItem) in the cookies.txt file. It
also extends ArrayList instead of including an ArrayList data member.
The find() method accepts a cookie flavour ID number and searches the CookieInventoryFile elements for a 
CookieInventoryItem with the same ID. If an item is found, that CookieInventoryItem is returned. If there 
is no item with that flavour ID, a null object (null) is returned.
The loadFromFile() method accepts a File object. The method reads all the records from the file and 
constructs a CookieInventoryItem object for each record. Each CookieInventoryItem object is added to the 
ArrayList inside the CookieInventoryFile.
The writeToFile() method accepts a File object. The method iterates through all of the CookieInventoryItem 
objects in the ArrayList and deconstructs them into a delimited string that can be written to the file.

UI Elements 
The application has the following UI elements:
-an HBox containing a label and a combo box that allows the user to choose a cookie flavour;
-text field where user enter purchased items and then clicks the SELL button. The sell button subtracts the 
input value from the selected cookie's quantity.
-text field where user enter additional numbers of items and then clicks the ADD button. This finds the 
matching CookieInventoryItem in the CookieInventoryFile list and adds the input value to the selected cookie's 
quantity.
-the exit button on an alert dialog box asking the user to exit the application.

Error Handling and Exceptions
I have implemented a number of efficient error handling codes. The following are;
-Empty text fields: if the user clicks Sell or Add when the text field is empty, an alert message is shown.
-Purchasing items not in inventory: if the user attempts to purchase cookies that aren't in inventory, an alert
message is shown.
-Purchasing more items than the quantity on hand: if the user attempts to purchase more of a certain flavour of 
cookie than is currently available in inventory, an alert message is shown.
-Entering 0 or negative values: if the user enters a 0 or negative quantity in either text field, an error is shown.
-Entering non-numeric values: if the user enters any non-numeric value in either text field, an error message is shown.
