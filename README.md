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

1) Application-Specific Commands

- Access only through 'driver' instance.
- Dynamically get title, current URL and source content of the page.
- .get() is a method
- .title, .current_url, .page_source -> not methods, but keyword variables (properties) built-in and availalbe in the 'driver' instance.

__driver.page_source__ -> Web Server generates/creates the HTML code which is presented to the user in the UI format. Use to do validations on HTML.

  - __get()__ - method to open the app URL
  - __title__ - get value of the current page title
  - __current_url__ - capture current URL of web page
  - __page_source()__ - capture source code of the page




