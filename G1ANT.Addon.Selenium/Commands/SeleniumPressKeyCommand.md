# selenium.presskey

**Syntax:**

```G1ANT
selenium.presskey  key ‴‴  search ‴‴ 

```

**Description:**

Command `selenium.presskey` types text into element. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`key`| "string":{TOPIC-LINK+string}| yes |   | key to press |
|`search`| "string":{TOPIC-LINK+string}| yes |   | phrase to find element by |
|`by`| "string":{TOPIC-LINK+string}| no |  | specifies an element selector, accepts 'name','text','title','class','id','selector','query','jquery' |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

`selenium.presskey` is an advanced search command that enables to find certain element on a webpage by 'name','text','title','class','id','selector','query','jquery'. When it finds the element, it performs certain action on it by pressing a key you choose.

```G1ANT
selenium.open type ‴firefox‴ url ‴duckduckgo.com‴
 selenium.type text ‴whale sharks‴ search ‴search_form_homepage‴ by ‴id‴
 selenium.presskey key ‴enter‴ search ‴search_button_homepage‴ by ‴id‴

```

First open a browser using `selenium.open` command.
Then use `selenium.type` command to  type a phrase you want to search - ‴whale sharks‴ and then find an element where the phrase will be typed ‴search_form_homepage‴. You can find the element using developer tools in your web browser. ‴whale sharks‴ will be typed inside of the search window that you chose by id.

!{IMAGE-LINK+2016-11-10-4}! 

The `selenium.open` command becomes handy now that you want to choose the 'search button' in the browser. Use developer tools in your web browser to choose the element and use it as the value for 'search' argument. Then type the 'key' argument. Usually you would use 'enter' as the value, but any button can be used. If you use 'enter' as in the example, G1ANT.Robot will press the search button for you automatically.

!{IMAGE-LINK+2017-11-07-selenium-presskey-search-button}!