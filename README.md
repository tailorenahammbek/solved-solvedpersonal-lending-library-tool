Download Link: https://assignmentchef.com/product/solved-solvedpersonal-lending-library-tool
<br>
Final Project Description In this project we will improve our personal lending library tool by (1) adding the ability to delete items from the library, (2) creating a graphical user interface that shows the contents of the library and allows the user to add, delete, check out, or check in an item, (3) using a file to store the library contents so that they persist between program executions, and (4) removing the 100 item size restriction. Sample Run The video final.swf on the course website shows a sample run of this program. Suggestions You have the freedom to design your program however you want, provided that it meets the requirements and follows good design principles. However, if you would like some ideas of where to start, they are provided in this section.  Modify the Library class to use an ArrayList rather than an array (to eliminate the size limit)  Rewrite all of the methods in the Library class that display error messages to throw exceptions  Add the following methods to the Library class:  public void delete(String title) – Removes the item with this title from the library (the ArrayList of MediaItems)  public void save() – Writes all of the items out to the data file library.txt. For each MediaItem, write its title, format, whether or not it is on loan (true/false), who it is loaned to (or null, if not on loan), and the date is was loaned (or null, if not on loan). Write out some weird symbol in between each of these things – be sure to pick something that is not likely to appear in a title or someone’s name.  public void open() – Reads in the data from library.txt, recreates the MediaItems, and puts them into the ArrayList. When you read in each line, you will need to tokenize it based on whatever symbol you picked. Then create a new MediaItem object and set the fields appropriately.  Create a JavaFX LibraryGUI class  This class should have a Library object as one of its fields. In the LibraryGUI constructor you will need to call the library constructor method to initialize this field and then call its open() method to read in the items from the data file.  Use a javafx.scene.control ListView class to display the contents of the library (see Chapter 16 of Liang, pp. 647-651, as well as http://www.javafxcookbook.com/home). The code below shows how to use the ListView control to display list of items (http://www.javafxcookbook.com/home). The control takes a data model (a sequence of items) as its data source. The code below shows how it is used: ListView { width:w-200 height:h-50 effect:DropShadow{offsetY:3 offsetX:3} items: for (i in [1..50]) “Cloud {%5s i}” } The snippet above would produce the ListView shown in the following figure:  Provide buttons for adding, deleting, checking in, and checking out items  Attach action listeners to the buttons that use dialog boxes to get any required information from the user and then call the appropriate method in the library. If the user currently has an item selected in the list, assume this is the item they want to check in/check out/delete. Hints When the user has an item in the list selected and they choose to check in, check out, or delete that item, you will need to get the item’s title in order to pass it to the appropriate library method. To do this, you can use the following code: Object selected = list.getSelectedValue(); // gets the selected item String s = selected.toString(); // converts that to a String String title = s.substring(0, s.lastIndexOf(“(“)); // extracts the title String title = title.trim(); // removes any trailing whitespace You will need to call the Library class’s save method when the user closes the application. Rubric (Each item is worth four points, for a total of 52)  The contents of the library persist across program executions  The program allows the user to delete items  The library is not limited to a set number of items  The entire program is handled through a graphical interface (e.g. the console is no longer used at all)  The GUI allows the user to see the contents of the library and add, delete, check in, and check out items  The GUI indicates which items are on loan  The user can choose which item to check in, check out, or delete by selecting it in the list rather than typing in the title  The contents of the list are kept in sync with the contents of the library  If an exception occurs, the program displays an appropriate error dialog box to the user  If the user tries to do something nonsensical, such as checking in an item that is not checked out, they are notified with an error dialog  The program compiles  The program follows good coding conventions and design guidelines  The program runs