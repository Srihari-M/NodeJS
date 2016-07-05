# About the App

  The "ToDo" App is a simple application which will do basic CRUD operations. It allows to add and persist ToDos
  that you need to get done. As you complete different  tasks in todo list you can delete or edit them from the list.
  The  tasks in the todo list are stored in a database.

  - UI contains the following components:
    - A text box to get input from the user. The input is sent in a POST request to the  server component, which inserts the text to the database.
    - The list of To-do’s inserted in the database is displayed. This data is retrieved using GET service call to the server component.
    - Edit icon along with each To-do entry to update the input in the text box.
	  - On saving, this data is sent as a PUT request to the server component, which updates the text in the database.
	  - On cancelling, no operation takes place.
    - Delete icon with each To-do entry to delete the entry from database using the DELETE service call.



# AngularJS

AngularJS is a structural framework for dynamic web apps. It lets you use HTML as your template language and lets you extend HTML's syntax to express your application's components clearly and succinctly. Angular's data binding and dependency injection eliminate much of the code you would otherwise have to write.

### Client File Structure
```
└── client
│      ├── assets
│      │   └── css
│      │   	    └── toDo.css
│      │   └── img
│      │   	    └── logo.png
│      ├── controllers
│      │   └── toDo.js
│      └── services
│      │   └── toDo.js
│      ├── tests
│      │   └── test.js
|      └── index.html
├── karma.conf.json
├── Gulpfile.js
├── manifest.yml
└── package.json

```
### Files related to AngularJS
The application folder structure is modular, so that our controller and all of our $http requests are in separate files. Having all of the functionality in different modules helps to understand the overall layout of the application, hence the re-use and testing of code is easy.

```
index.html  # Includes all the scripts and styles and contains the HTML code to render the To Do application.
```
**assets**
```
css         # Contains the styles information required for the UI
img         # Contains the static images which are displayed in the UI
```

**controller**
```
toDo.js     # This is the Angular module containing the button actions and assigning of scope variables. This has all the code to get, create, update or delete a to-do inside our service.
```

**services**
```
toDo.js     # This is the service module and is meant to interact with our Node API. All the service calls are present in this file. This ensures that we can test this code separate of our overall application.
```


### Unit Testing and Code Coverage

The unit tests in this application are written using jasmine and karma tools. In this project, gulp is the task runner used to execute all the test cases and code coverage.

```
karma.conf.js   # Contains the configuration for the karma tool to execute the jasmine test cases.
```
**tests**
```
test.js         # Contains all the test cases to test the CRUD operations present in the controller. It also tests all the actions of buttons and if the data is reflected appropriately in DOM elements.
```

In order to execute the UI Test cases, the following command must be executed in command prompt. This command uses the GulpFile present in the root folder of the project. It takes the configuration from karma.conf.json present in the root folder. This file contains the list of files to be included for testing and other plugin information.

```sh
$ gulp test_UI
```
After executing the above command, the test results will be displayed in the command prompt and the coverage report will be present in the *\client\tests\results\coverage* folder.
