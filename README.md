# WebDriver Commands

WebDriver actions/methods/functions/commands to perform operations.

WebDriver Commands Categories:
1) get commands / application commands
2) conditional commands
3) browser commands
4) navigational commands
5) wait coomands

__get__ commands are for getting info like a page title, URL, HTML source code, etc. Can call them Application-Related Commands - get app, URL, title, etc. 
In Selenium Java, they are called Get Commands, because they start with __get__ keyword. There's no such thing in Python. I can directly call title(), current_url(), page_source(), etc.

__1) Application-Specific Commands__

- Access only through 'driver' instance.
- Dynamically get title, current URL and source content of the page.
- .get() is a method
- .title, .current_url, .page_source -> not methods, but keyword variables (properties) built-in and availalbe in the 'driver' instance.

__driver.page_source__ -> Web Server generates/creates the HTML code which is presented to the user in the UI format. Use to do validations on HTML.

  - __get()__ - method to open the app URL
  - __title__ - get value of the current page title
  - __current_url__ - capture current URL of web page
  - __page_source()__ - capture source code of the page


__2) Conditional Commands__

- Belong to WebElement. Access the commands from WebElement, not 'driver' instance. Don't write 'driver.is_displayed()'.
- Check the presence of an element on the page. Check/verify conditions, validate at the element level.
- Return Boolean values - True or False.

[Difference between is_displayed() and is_present()](https://stackoverflow.com/questions/28119084/what-is-the-difference-between-the-ispresent-and-isdisplayed-methods)

  - __is_displayed()__ - check if element is present/available
  - __is_enabled()__ - if disabled, can't perform any action
  - __is_selected()__ - radiobuttons / checkboxes

Before inputting text into a text box, I want to verify is the box is there or not.

Before selecting a radiobutton/checkbox, if I run command __is_selected()__ it returns False. After selecting, it returns True.

__is_selected()__ is for Radiobuttons and Checkboxes

__is_displayed__ and __is_enabled__ are for all kinds of elements.



#TODO

__3) Browser Commands__

__4) Navigational Commands__

__5) Wait Commands__

