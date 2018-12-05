# Hybrid Mobile Screenshot Automation Tool

Use this tool to automate the process of create stardar screenshots (portrail and landscape) ready to upload to the Android and/or Applestore.

Available for Mac and Windows

This command-line tool is specially useful to automatize the tedious process of taking screenshot of your hybird application specially when you support multiples language.

# Step 1
Download the binary file

# Step 2
Create an instructions file where you going to specify all the instructions to take the screenshots

### Instructions structure
command + :: + parameter

In case we need more than one parameter then use :;: to separate the param 
command + :: + param1 :;: param2

### FullExample

- url::http://localhost:8100/#/login
- wait::6000
- screenshot::true
- wait::1000
- text::div.login-container > form > ion-item:nth-child(1) > div.item-inner > div > ion-input > input:;:email@email.com
- wait::1000
- text::div.login-container > form > ion-item:nth-child(2) > div.item-inner > div > ion-input > input:;:password
- wait::1000
- tap::ion-content > div.scroll-content > div.login-container > form > div > button
- wait::7000
- screenshot::true
- wait::1000
- url::http://localhost:8100/#/photos
- wait::1000
- tap::button.toast-button
- wait::20000
- screenshot::true
- wait::1000
- hold::body > ion-app > ng-component > ion-nav > page-photos > ion-content > div.scroll-content > ion-grid > ion-row > ion-col:nth child(5) img
- wait::1000
- screenshot::true
- wait::1000
- tap::body > ion-app > ion-action-sheet > div > div > div:nth-child(1) > button:nth-child(3)
- wait::6000
- screenshot::true
- wait::1000
- scroll::ion-nav > page-azure-face-recognition > ion-content:;:-1
- wait::1000
- screenshot::true
- wait::1000


## The list of avalible commands for the interaction 
+ url (Specifies the url you want to navigate to)
+ wait (wait for the specied time in milliseconds)
+ screenshot (Takes a screenshot)
+ text (send text string to specified css selector)
+ tap (send click on specified css selector)
+ hold (send hold event to css selector)
+ scroll (scroll on css selector, uses negative number to scroll downand positive to scroll up)





