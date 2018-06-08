# selenium.setattribute

**Syntax:**

```G1ANT
selenium.setattribute  name ‴‴ search ‴‴

```

**Description:**

Command `selenium.setattribute` sets specified attribute of specified element. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`name` | "string":{TOPIC-LINK+string}| yes |  | name of attribute to set value of |
|`search` | "string":{TOPIC-LINK+string}| yes |  | phrase to find element by |
|`value` | "string":{TOPIC-LINK+string}| no |  | value to set  |
|`by`| "string":{TOPIC-LINK+string}| no | | specifies an element selector, accepts 'name','text','title','class','id','selector','query','jquery' |
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutselenium":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Selenium.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium":https://github.com/G1ANT-Robot/G1ANT.Addon.Selenium

**Example 1:**
 
```G1ANT
selenium.open type ‴firefox‴ url ‴duckduckgo.com‴
selenium.setattribute name ‴class‴ value ‴hidden‴ search ‴logo_homepage_link‴ by ‴id‴

```

This command enables to search for certain element on a web page and set an attribute for it. In our example we are causing the logo disappear by setting a 'hidden' class for the logo.
To set an attribute we need to catch an element first. In order to do that, please check developer tools. 

**search** argument expects the value of **by** argument, which could be 'id', 'class', etc. In our case the value of **search** argument is ‴logo_homepage_link‴
**name** argument expects 'class', 'id', etc. and **value** argument defines what should happen with the element that we catch.  
HTML tag for the logo is:
`&lt;a id = "logo_homepage_link" class = "logo_homepage" href = "/about"&gt;&lt;/a&gt;`

!{IMAGE-LINK+2017-11-15-selenium-setattribute}! 

**Example 2:**

Other way of catching the same element is by 'class'.

```G1ANT
selenium.open type ‴firefox‴ url ‴duckduckgo.com‴
selenium.setattribute name ‴class‴ value ‴invisible‴ search ‴logo_homepage‴ by ‴class‴

```

**Example 3:**

```G1ANT
selenium.open type ‴firefox‴ url ‴duckduckgo.com‴
selenium.setattribute name ‴class‴ value ‴width:0‴ search ‴logo_homepage‴ by ‴class‴

```

**Example 4:**

```G1ANT
selenium.open type ‴chrome‴ url ‴duckduckgo.com‴
selenium.setattribute name ‴style‴ value ‴background-color: red;‴ search ‴search-wrap--home‴ by ‴class‴

```

This command will perform the same action as you could achive using jQuery `$(".search-wrap--home")[0].setAttribute("style", "background-color: red;")`