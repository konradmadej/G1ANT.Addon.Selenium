selenium.click
*Syntax:*

bc. selenium.click  search ‴‴ 

*Description:*

Command @selenium.click@ clicks an element on an active webpage. 

|_. Argument |_. Type |_. Required |_. Default Value |_. Description |
|@search@| "string":{TOPIC-LINK+string}| yes |  | phrase to find element by |
|@by@| "string":{TOPIC-LINK+string}| no |  | specifies an element selector, accepts 'name','text','title','class','id','selector','query','jquery' |
|@if@| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|@timeout@| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|@errorjump@ | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given @timeout@ expires |
|@errormessage@| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no @errorjump@ argument is specified |

For more information about @if@, @timeout@, @errorjump@ and @errormessage@ arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in *G1ANT.Addon.Selenium.dll*.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

*Example 1:*

This example shows how to print an element from a website using @selenium.click@ command. Open a web browser, then maximize the window. @selenium.click@ searches for the class of the 'print button' and clicks this element. The element could also be searched by 'name','text','title','class','id','selector','query','jquery'. In order to search any element on a website using @selenium.click@ command, you need to use web browser developer tools.

bc. selenium.open type ‴chrome‴ url ‴https://www.cia.gov/library/publications/the-world-factbook/geos/dj.html‴
window title ‴✱Factbook✱‴ style ‴maximize‴
selenium.click search ‴printVersion‴ by ‴class‴
keyboard ⋘CTRL+P⋙
keyboard ⋘ENTER⋙ 

!{IMAGE-LINK+2017-11-14-selenium-click}!