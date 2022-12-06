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

__3) Browser Commands__

1) close()
2) quit()

These are browser-level, not application-level, commands. I can start an app __after__ launching the browser. Application (Get) Commands work only when I open the app.

When I have one browser window open, both commands work in a similar way, they close the open browser. There is an internal difference:
  - __close()__ command closes the browser, but still the browser-specific internal process keeps on running in the backend. That process does not get killed. Analogy: In every OS (Windows or Mac), when I start an app there are some processes created internally.
    - closes a single browser window/tab, where the driver's focused
  - __quit()__ command also gets the internal driver process killed in the background.
    - closes multiple browser windows

When I click on a link on a page, the browser opens another Child window When I perform driver.close() only the Parent window - original window that got opened with the URL - gets closed. The Child window - window triggered by the link in the Parent window - stays open. 
My browser focus stays on the Parent app window. even though a statement (link click) opens another app in another browser window, still my driver focus is on the first Parent app. The focus of the driver does not directly shift to the second app. The browser window, on which the driver is focused, that particular window gets closed with __close()__ command. __close()_ command closes only one browser windows at a time. If I have two windows open, it will not close both. It will close only one (Parent window), on which the driver is focused. Whether I have 10 or 50 windows open, it closes only one.

Internally, for each browser window a process ID gets created as soon as I initialize the process. Eg, some prcoesses may be created by the OS. When I launch my browser from the device, there is a process created by the OS. Similarily, when I open another tab, there is another process. Another tab creates yet another process, ans so on. Eg, for evey action Windows creates a process.

__quit()__ command internally kills the driver processes, which are not physically visible.That's the reason it can close/kill __all__ the browser windows.

Scenario: My requirement is to close a window of choice from among 10 browser windows. -> Use __window_handles()__ command.

__4) Navigational Commands__

- back()
- forward()
- refresh()

Access these commands through the 'driver' instance.

When I enter one URL in the browser and then another URL in the same browser, the browser remembers both URLs.
 - Navigate Back and Forward using left ⇦ and right ⇨ arrows in the browser.
 - Refresh/reload the browser by using the Refresh 🔄 button in the browser.

        driver.get("url1")
        driver.get("url2")
        driver.back()       # go back to url1
        driver.forward()    # go to url2
        driver.refresh()

Through 'driver' instance I can access Application-Level, Browser and Navigational Commands.

Only the Conditional Commands must be access through the WebElement.


[__What's the Difference between find_element() and find_elements()?__](https://github.com/lana-20/webdriver-commands/blob/main/find_element()%20vs%20find_elements().pdf)

__.text__ extracts/gets the value of an element. There's another method __.get_attribute('value')__.

[__What's the Difference between .text and .get_attribute('value')?__](https://github.com/lana-20/webdriver-commands/blob/main/_text%20vs%20.get_attribute().pdf)


__5) [Wait Commands](https://github.com/lana-20/webdriver-commands/blob/main/Wait%20Commands.pdf)__

