selenium.type
*Syntax:*

bc. selenium.type  text ‴‴  search ‴‴ 

*Description:*

Command @selenium.type@ types text into an element. 

|_. Argument |_. Type |_. Required |_. Default Value |_. Description |
|@text@| "string":{TOPIC-LINK+string}| yes |   | text to type |
|@search@| "string":{TOPIC-LINK+string}| yes |   | phrase to find element by |
|@by@| "string":{TOPIC-LINK+string}| no |  | specifies an element, accepts ‘name’,‘text’,‘title’,‘class’,‘id’,‘selector’,‘query’,‘jquery’ |
|@if@| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|@timeout@| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|@errorjump@ | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given @timeout@ expires |
|@errormessage@| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no @errorjump@ argument is specified |

For more information about @if@, @timeout@, @errorjump@ and @errormessage@ arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in *G1ANT.Addon.Selenium.dll*.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

*Example 1:*

bc. selenium.open type ‴chrome‴ url ‴duckduckgo.com‴
selenium.type text ‴robotic process automation‴ search ‴search_form_input_homepage‴ by ‴id‴
selenium.click search ‴search_button_homepage‴ by ‴id‴
selenium.type text ‴ g1ant‴ search ‴search_form_input‴ by ‴id‴
selenium.presskey key ‴enter‴ search ‴search_button‴ by ‴id‴