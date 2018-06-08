# selenium.gettitle

**Syntax:**

```G1ANT
selenium.gettitle

```

**Description:**

Command `selenium.gettitle` gets title of currently active web browser instance.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`result`| "variable":{TOPIC-LINK+variable}| no | "♥result":{TOPIC-LINK+common-arguments} | name of variable where title of currently attached web browser instance will be stored |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutcommand":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

```G1ANT
selenium.open type ‴firefox‴ url ‴google.com‴
selenium.gettitle result ♥title
dialog ♥title

```

!{IMAGE-LINK+2017-11-15-selenium-gettitle}! 

**Example 2:**

```G1ANT
selenium.open type ‴firefox‴ url ‴facebook.com‴
selenium.gettitle result ♥title
dialog ♥title

```