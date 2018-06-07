selenium.getattribute
*Syntax:*

bc. selenium.getattribute  name ‴‴  search ‴‴ 

*Description:*

Command @selenium.getattribute@ gets specified attribute of specified element.

|_. Argument |_. Type |_. Required |_. Default Value |_. Description |
|@name@| "string":{TOPIC-LINK+string}| yes |  | name of attribute to obtain value of |
|@search@| "string":{TOPIC-LINK+string}| yes |  | phrase to find element by |
|@by@| "string":{TOPIC-LINK+string}| no |  | specifies an element selector, accepts 'name','text','title','class','id','selector','query','jquery' |
|@result@| "variable":{TOPIC-LINK+variable}| no | "♥result":{TOPIC-LINK+common-arguments} | name of variable where value of specified attribute will be stored |
|@if@| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|@timeout@| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|@errorjump@ | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given @timeout@ expires |
|@errormessage@| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no @errorjump@ argument is specified |

For more information about @if@, @timeout@, @errorjump@ and @errormessage@ arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in *G1ANT.Addon.Selenium.dll*.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

*Example 1:*

bc. selenium.getattribute@ command lets you get the attribute of any element on a web page and stores the result inside of a variable. In our example it searches by 'id' which name is 'content' and the result is 'class' of this element, in this case 'style-scope ytd-app'. Full HTML expression for this element is @&lt;div id='content' class='style-scope ytd-app'&gt;...&lt;/div&gt;

*Example 2:*

bc. selenium.open type ‴chrome‴ url ‴youtube.com‴
selenium.getattribute name ‴class‴ search ‴content‴ by ‴id‴ result ♥attribute
dialog ♥attribute
selenium.close