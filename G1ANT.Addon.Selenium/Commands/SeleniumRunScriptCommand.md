# selenium.runscript

**Syntax:**

```G1ANT
selenium.runscript  script ‴‴ 

```

**Description:**

Command `selenium.runscript` runs Javascript inside the web browser. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`script` | "string":{TOPIC-LINK+string} | yes |  | script which will be used inside web browser |
|`result` | "variable":{TOPIC-LINK+variable} | no |  "♥result":{TOPIC-LINK+common-arguments} | stores the result of the command in a variable |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

In this example, G1ANT.Robot opens 'google.com' and uses Javascript to return **.tagName** of some component on a web page. In our case the component is 'body'. And to select this 'body' element we need to use Javascript structure- **document.querySelector("body")**. It is a standard Javascript syntax used while choosing elements on a web page. 
Please, bear in mind it is crucial to use **return** word before Javascript syntax.

```G1ANT
selenium.open type ‴firefox‴ url ‴google.com‴
selenium.runscript script ‴return document.querySelector("body").tagName‴ result ♥result2
dialog ♥result2

```