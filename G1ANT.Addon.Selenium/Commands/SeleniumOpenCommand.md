# selenium.open

**Syntax:**

```G1ANT
selenium.open  type ‴mozilla‴ 

```

**Description:**

Command `selenium.open` opens new instance of chosen web browser and optionally navigates to specified url address. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`type`| "string":{TOPIC-LINK+string}| yes|  | name of the web browser |
|`url`| "string":{TOPIC-LINK+string}| no|  | web page address to be loaded |
|`nowait` | "nowait":{TOPIC-LINK+boolean}| no | false | waits until the webpage fully loads  |
|`result` | "variable":{TOPIC-LINK+variable}| no | "♥result":{TOPIC-LINK+common-arguments} | stores the result of the command in a variable |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

```G1ANT
selenium.open type ‴firefox‴ url ‴https://www.google.co.uk/search?q=g1ant‴

```

!{IMAGE-LINK+2016-11-11-1}! 

**Example 2:**

This example opens website and waits 5 seconds (using `delay` command) till it will be loaded, afterwards `keyboard` command emulates TAB key pressed two times then ENTER. Finally "http://irpaai.com/membership/" will be opened.

```G1ANT
selenium.open type ‴firefox‴ url ‴www.irpanetwork.com‴
delay 5
keyboard ⋘tab 2⋙⋘enter⋙

```