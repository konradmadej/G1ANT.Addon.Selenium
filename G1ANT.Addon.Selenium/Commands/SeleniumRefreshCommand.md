selenium.refresh
*Syntax:*

bc. selenium.refresh

*Description:*

Command @selenium.refresh@ refreshes the web browser.

|_. Argument |_. Type |_. Required |_. Default Value |_. Description |
|@if@| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|@timeout@| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|@errorjump@ | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given @timeout@ expires |
|@errormessage@| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no @errorjump@ argument is specified |

For more information about @if@, @timeout@, @errorjump@ and @errormessage@ arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in *G1ANT.Addon.Selenium.dll*.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

*Example 1:*

bc. selenium.open type ‴firefox‴ url ‴duckduckgo.com‴
selenium.refresh