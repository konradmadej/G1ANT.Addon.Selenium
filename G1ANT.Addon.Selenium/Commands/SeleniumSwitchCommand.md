# selenium.switch

**Syntax:**

```G1ANT
selenium.switch  id ‴‴

```

**Description:**

Command `selenium.switch ` changes current active web browser instance. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`id`| "integer":{TOPIC-LINK+integer}| yes |  | ID of web browser  |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

`selenium.switch` command enables switching between opened browsers. See the example below where we open 'firefox' and 'chrome' giving each of the opened browsers a **result** argument and store its value in a variable. `selenium.switch` allows us to switch between the browsers when we set and **id** argument as certain value, in our case '♥nasa'.

```G1ANT
selenium.open type ‴firefox‴ url ‴https://www.nasa.gov‴ nowait true result ♥nasa
selenium.open type ‴chrome‴ url ‴google.com‴ result ♥google
selenium.switch id ♥nasa

```