# watson.speechtotext

**Syntax:**

```G1ANT
watson.speechtotext  path ‴‴  login ‴‴  password ‴‴

```

**Description:**

Command `watson.speechtotext` allows to transcript speech from audio file. 

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`path`| "string":{TOPIC-LINK+string} | yes |  | specifies path to file with speech recorded | 
|`login`| "string":{TOPIC-LINK+string} | yes |  | specifies service's login |  
|`password`| "string":{TOPIC-LINK+string} | yes |  | specifies service's password |  
|`result`| "variable":{TOPIC-LINK+variable} | no |  "♥result":{TOPIC-LINK+common-arguments} | returns most likely text transcription of the speech, recognised by Artificial Intelligence |  
|`threshold`| "float":{TOPIC-LINK+decimal} | no | | floating point value that specifies the minimum score a class must have to be displayed in the results, between 0 and 1 |  
|`language`| "string":{TOPIC-LINK+string} | no | | specifies language of speech | 
|`if`| "bool":{TOPIC-LINK+boolean}| no | true | runs the command only if condition is true |
|`timeout`| "variable":{TOPIC-LINK+variable}| no | "♥timeoutwatson":{TOPIC-LINK+special-variables} | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | "label":{TOPIC-LINK+label}| no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| "string":{TOPIC-LINK+string}| no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit "Common Arguments":{TOPIC-LINK+common-arguments} manual page.

This command is contained in **G1ANT.Addon.Watson.dll**.
See: "https://github.com/G1ANT-Robot/G1ANT.Addon.Watson":https://github.com/G1ANT-Robot/G1ANT.Addon.Watson

**Generating login and password:**

In order to generate the required arguments- **login** and **password** for `watson.speechtotext` command, we need to follow the instructions below:

1. Log in to IBM Watson account using previously created account. In order to see how to create an account, please go to "watson commands":{TOPIC-LINK+watson-commands}
!{IMAGE-LINK+5}! 
2. Press **Create resource** button
!{IMAGE-LINK+6}! 
3. Press **Speech to Text** option
!{IMAGE-LINK+7}! 
4. Choose the plan and press **Create** button
!{IMAGE-LINK+8}! 
5. Go to dashboard using link 'https://console.bluemix.net/dashboard/apps'
6.  Hover over **Speech to Text** and press it
!{IMAGE-LINK+10}! 
!{IMAGE-LINK+11}! 
7. Go to **Service credentials** on the left side menu tab
8. Press **New credential** button
!{IMAGE-LINK+12}! 
9. Press **Add** button
!{IMAGE-LINK+13}! 
10. Roll out the **View credentials** menu in the bottom
!{IMAGE-LINK+14}! 
11. You can now see the **username** and **password** that can be used as login and password in `watson.speechtotext` command
!{IMAGE-LINK+15}! 

**Example 1:**

```G1ANT
watson.speechtotext path ‴C:\SomeFolder\speechFile.wav‴ language ‴en-US‴ threshold 0.6

```