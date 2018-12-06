# Hybrid Mobile Screenshot Automation Tool

Use this tool to automate the process of create stardar screenshots (portrail and landscape) ready to upload to the Android and/or Applestore.

**This tool is in active development and beta version. If something seems off, create an issue!**

Available for Mac and Windows

This command-line tool is specially useful to automatize the tedious process of taking screenshot of your hybird application specially when you support multiples language.

# Step 1
Download and install (if not already installed) the dotNet SDK for your platform (Win/Linux/Mac) [here](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial)

# Step 2 
Download and extract the files from this repo, in your local machine

# Step 3
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
+ **url** (Specifies the url you want to navigate to)
+ **wait** (wait for the specied time in milliseconds)
+ **screenshot** (Takes a screenshot)
+ **text** (send text string to specified css selector)
+ **tap** (send click on specified css selector)
+ **hold** (send hold event to css selector)
+ **scroll** (scroll on css selector, uses negative number to scroll downand positive to scroll up)

# Step 4
Run the program:

```
**generic**
$ dotnet hybridAutoScreenshot.dll instructions.txt <ios/android/all> <language (en-US)>
```

```
$ dotnet hybridAutoScreenshot.dll path/to/your/file/instructions.txt ios en-US
```

```
$ dotnet hybridAutoScreenshot.dll instructions.txt android es-ES
```

To use the default values just run the command andit ill look for an **instructions.txt** file in the same directory of the program, **all** platforms and **en-US** language 

```
$ dotnet hybridAutoScreenshot.dll
```
# Example:

The following exmple was made using our premiun starter **ionAppFullPlus** uisng the gallery section that is integrated with Azure face recognition to illustrate how this tool works, in this example we implemented/used all the commands availables 

![alt text](https://s3.amazonaws.com/ionic-marketplace/ionappfullplus/icon.png "Logo ionAppFullPlus")

[ionAppFullPlus](https://market.ionicframework.com/starters/ionappfullplus)




