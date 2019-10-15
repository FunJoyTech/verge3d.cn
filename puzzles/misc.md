# Misc

Miscellaneous puzzles to perform various operations on a high level.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc.jpg)

### **"open web page"**

When this puzzle is triggered, a specified URL is opened in a new or in the same browser tab depending on the drop-down selection. When triggered from the Puzzles editor, it will ask for a user confirmation before leaving the tab.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-open-web-page.jpg)

### **"social share link"**

Generates a link for sharing your application in popular social media.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-social-share-link.jpg)

### **"call JS function"**

Executes a function specified in the JavaScript code of the application. Optionally passes parameters to be used as function arguments.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-call-js-function.jpg)

In order to add a function to JavaScript code, open the application **.js** file \(for example, my\_awesome\_app.js located in verge3d/applications/my\_awesome\_app\) with any text editor. Search for "prepareExternalInterface" and add your function inside that declaration \(between the curly brackets\), so that it looks like this:`function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function(numericArg, textArg) { alert('Got some params from Puzzles: ' + numericArg + ' and ' + textArg); } }`

### **"when called from JS"**

Allows for triggering Puzzles from the JavaScript code of the application. Optionally retrieves parameters passed from the JavaScript code and saves them as variables to be used by puzzles in the "do" slot.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-when-called-from-js.jpg)

In order to trigger this puzzle from the JavaScript code, open the application **.js** file \(for example, my\_awesome\_app.js located in verge3d/applications/my\_awesome\_app\) with any text editor. Search for "runCode" and add a function call inside that declaration \(between the curly brackets\), so that it looks like this:`function runCode(app) { app.ExternalInterface.myJSCallback('Hello, Puzzles!', 80); }`

### **"load data"**

Attempts to load data from a specified location. The puzzles in the "once ready do" slot are interpreted regardless of whether the attempt was a success. The retrieved data can be accessed via the [loaded data](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#loaded_data) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-load-data.jpg)

### **"send data"**

Attempts to send a specified data to a remote location using an asynchronous [POST HTTP](https://en.wikipedia.org/wiki/POST_%28HTTP%29) request. The puzzles in the "once ready do" slot are interpreted regardless of whether the attempt was a success. If there is any response data, it can be accessed via the [loaded data](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#loaded_data) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-send-data.jpg)

### **"loaded data"**

Returns data retrieved by the [load data](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#load_data) or [send data](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#send_data) puzzles.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-loaded-data.jpg)

### **"read JSON"**

Interprets text as [JavaScript Object Notation](https://en.wikipedia.org/wiki/JSON#Example) data which are returned in a dictionary.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-read-JSON.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#read_CSV)

### **"read CSV"**

Interprets text as [comma-separated values](https://en.wikipedia.org/wiki/Comma-separated_values#Example). Returns a list of table rows, with each row represented as a list of values. The delimiter can be selected with the drop-down to correspond a CSV file's export settings. "From row" value denotes how many rows will be skipped starting from the top.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-read-CSV.jpg)

Table rows and values are accessed by their numeric indices starting from 0.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-csv-example.jpg)

### **"save state"**

Saves the state of specified objects and/or the values of variables specified by their names. The objects are cloned and stored in memory. The values of the variables are retrieved and stored in memory for each specified variable name.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-save-state.jpg)

If this puzzle is called several times, the states are saved in sequence so that it is possible to return to any previous state with the [undo state](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#undo_state) puzzle.

### **"undo state"**

Restores the state of objects and/or variables saved with the [save state](https://www.soft8soft.com/docs/manual/en/puzzles/Misc.html#save_state) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-undo-state.jpg)

If this puzzle is called several times, the states are restored from the saved sequence \(if any\) which makes it possible to return to any previously saved state from the stack.

### **"all variable names"**

Returns a list with the names of all variables used in Puzzles.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-all-variable-names.jpg)

### **"variable value by name"**

Returns the value of a variable specified by its name. This puzzle works similarly to the standard variable value puzzle, yet does not require to select a variable from the predefined dropdown menu.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-variable-value-by-name.jpg)

### **"place order"**

Composes a hidden order form with the "title", "contents" and "total price" fields and an optional screenshot and submits this form to a specified URL according to the specification explicated in the Wordpress Plugin section. By default the order form is submitted to the [demo ordering page](https://sandbox.soft8soft.com/order-form/).

Verge3D comes with a free Wordpress plug-in that is able to handle requests submitted by this puzzle. Upon receiving such a request, this Wordpress plug-in renders a page with an extended form supplemented with contact and comments fields, the embedded screenshot and a captcha. Filled out form is finally submitted by the customer and a new order is created in Wordpress admin interface. Both the customer and the sales manager are notified about the order by e-mail.

Please refer to the Wordpress Plugin section of this Manual for setup information.

Be sure to enable screenshots in the [configure application](https://www.soft8soft.com/docs/manual/en/puzzles/Initialization.html#configure_application) puzzle otherwise the screenshot may be rendered in black.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-place-order.jpg)

