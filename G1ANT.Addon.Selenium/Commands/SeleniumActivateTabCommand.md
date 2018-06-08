# selenium.activatetab

**Syntax:**

```G1ANT
selenium.activatetab  search ‴‴  

```

**Description:**

Command `selenium.activatetab` activates browser's tab. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`search`| "string":{TOPIC-LINK+string}| yes |  | tab searching text |
|`by`| "string":{TOPIC-LINK+string}| yes|  | tab searching constraint, accepts 'title' or 'url' |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

In order to check how this command works, we should open the browser first, then open a few new tabs. `selenium.activatetab` will open tab based on the values of **search** and **by** arguments.

```G1ANT
selenium.open type ‴firefox‴ url ‴wp.pl‴ result wp
 selenium.newtab url ‴facebook.com‴
 selenium.newtab url ‴google.com‴
 dialog message ‴newtab works if google.com is opened‴
 selenium.activatetab search ‴wp‴ by ‴url‴

```