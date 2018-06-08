# selenium.waitforvalue

**Syntax:**

```G1ANT
selenium.waitforvalue  script ‴‴  expectedvalue ‴‴ 

```

**Description:**

Command `selenium.waitforvalue` waits for javascript code to return specified value. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`script`| "string":{TOPIC-LINK+string}| yes |  | pass the full script as string to get it evaluated in browser |
|`expectedvalue`| "string":{TOPIC-LINK+string}| yes |  | value that we expect script will return |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

`selenium.waitforvalue` lets us check if the element on the web page is fully loaded so that G1ANT.Robot can perform further actions. It is useful when you want to make sure that certain element is already loaded before you start typing inside of it.

```G1ANT
selenium.open type ‴chrome‴ url ‴google.com‴
selenium.waitforvalue script ‴return document.querySelectorAll('#lst-ib').length &gt; 0‴ expectedvalue ‴true‴ timeout 20000 
selenium.type text ‴fluffy robots‴ search ‴lst-ib‴ by ‴id‴
selenium.close

```