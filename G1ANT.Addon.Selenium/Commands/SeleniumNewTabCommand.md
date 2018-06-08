# selenium.newtab

**Syntax:**

```G1ANT
selenium.newtab 

```

**Description:**

Command `selenium.newtab` creates new tab in current browser. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`url`| "string":{TOPIC-LINK+string}| no|  | webpage address to load |
|`nowait` | "bool":{TOPIC-LINK+boolean}| no | false | waits until the web page fully loads |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**

In order to check how this command works, we should open the browser first, then open a few new tabs using  `selenium.newtab` command.

```G1ANT
selenium.open type ‴firefox‴ url ‴wp.pl‴ result ♥wp
 selenium.newtab url ‴facebook.com‴
 selenium.newtab url ‴google.com‴

```

**Example 2:**

In this example you can see that the browser initially waits until ‴http://www.bbc.com/news‴ loads (default value is false, so G1ANT.Robot waits until the webpage fully loads) and then G1ANT.Robot opens ‴https://www.theguardian.com/international‴ without waiting for ‴amazon.com‴ to fully load.

```G1ANT
selenium.open type ‴firefox‴ url ‴http://www.bbc.com/news‴ 
selenium.newtab url ‴amazon.com‴ nowait true
selenium.newtab url ‴https://www.theguardian.com/international‴
selenium.activatetab search ‴bbc‴ by ‴url‴

```