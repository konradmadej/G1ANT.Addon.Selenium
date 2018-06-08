# watson.classifyimage

**Syntax:**

```G1ANT
watson.classifyimage  rectangle ‴‴  apikey ‴‴

```

**Description:**

Command `watson.classifyimage` allows to capture part of the screen and classify the image that was captured. Class scores range from 0 - 1, where a higher score indicates greater likelihood of the class being depicted in the image.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`rectangle`| "string":{TOPIC-LINK+string} | yes |  | specifies capture screen area in format ‴x0//y0//x1//y1‴ |
|`apikey`| "string":{TOPIC-LINK+string} | yes |  | specifies api key needed to login to the service |
|`relative`| "bool":{TOPIC-LINK+boolean}| no | true  | if set to true, rectangle's position relates to currently focused window|
|`threshold`| "float":{TOPIC-LINK+decimal}| no | 0 | floating point value that specifies the minimum score a class must have to be displayed in the results, between 0 and 1 |
|`result`| "variable":{TOPIC-LINK+variable}| no | "♥result":{TOPIC-LINK+common-arguments} | returns semicolon separated pairs of classes and score values, recognised by Artificial Intelligence|
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutwatson":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Watson.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Watson":https://github.com/G1ANT-Robot/G1ANT.Addon.Watson

**Generating apikey**

In order to generate the required argument- apikey for `watson.classifyimage` command, we need to follow the instructions below:

1. Log in to IBM Watson account under this link: 'https://console.bluemix.net/login' using previously created account. In order to see how to create an account, please go to "watson commands":{TOPIC-LINK+watson-commands}. 
2. Press **create resource** button
!{IMAGE-LINK+17}! 
3. Hover over and press **Visual Recognition** option
!{IMAGE-LINK+18}! 
4. Choose **PLAN**
!{IMAGE-LINK+19}! 
5. Press **Create** button
!{IMAGE-LINK+20}! 
6.Go to **Service credentials** on the left side menu tab
!{IMAGE-LINK+21}! 
7. Press **New credential** button
!{IMAGE-LINK+22}! 
8.Press **Add** button
!{IMAGE-LINK+23}! 
9. Press **view credential**
10. Now you can see an **apikey** that can be used in `watson.classifyimage` command
!{IMAGE-LINK+24}! 

**Example 1:**

```G1ANT
watson.classifyimage rectangle ‴480⫽244⫽1439⫽848‴ relative false

```

!{IMAGE-LINK+oranges}! 

results in below classification: 
orange:0,911;citrus:0,927;fruit:0,927;navel orange:0,748;vitamin:0,554;orange color:1;

**Example 2:**

```G1ANT
watson.classifyimage rectangle ‴480⫽244⫽1439⫽848‴ relative false threshold 0.9

```

!{IMAGE-LINK+owl}! 

results in below classification: 
owl:0,961;bird of prey:0,962;bird:0,962;animal:0,962;