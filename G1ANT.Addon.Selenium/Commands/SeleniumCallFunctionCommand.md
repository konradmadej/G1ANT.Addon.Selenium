selenium.callfunction
*Syntax:*

bc. selenium.callfunction  functionname ‴‴ search ‴‴ 

*Description:*

Command @selenium.callfunction@ calls function on specified element. 

|_. Argument |_. Type |_. Required |_. Default Value |_. Description |
|@functionname@| "string":{TOPIC-LINK+string}| yes |  | name of function to call |
|@search@| "string":{TOPIC-LINK+string}| yes |  | phrase to find element by |
|@parameters@| "string":{TOPIC-LINK+string}| no |  | parameters to be passed to the function | 
|@type@| "string":{TOPIC-LINK+string}| yes |  | function call type, either ‴javascript‴ or ‴jquery‴ |
|@by@| "string":{TOPIC-LINK+string}| no |  | specifies an element, accepts 'name','text','title','class','id','selector','query','jquery' |
|@if@| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|@timeout@| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|@errorjump@ | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given @timeout@ expires |
|@errormessage@| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no @errorjump@ argument is specified |

For more information about @if@, @timeout@, @errorjump@ and @errormessage@ arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in *G1ANT.Addon.Selenium.dll*.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

*Example 1:*

bc. selenium.open type ‴chrome‴ url ‴msn.com‴ timeout 30000
list.create text ‴aa‴ result ♥list
selenium.callfunction search ‴q‴ by ‴id‴ functionname ‴val‴ parameters ♥list type ‴jquery‴ 
selenium.runscript script ‴return $('#q').val();‴ result ♥result
dialog ♥result