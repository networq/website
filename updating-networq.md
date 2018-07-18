---
status: draft
spellChecked:
author: j.faassen@linkorb.com
editor: masterbunny@gmail.com
notes:
  - Needs path adjustment instructions for Linux/Mac
---

## Updating NetworQ-web

### 1. Update networkq-web

Set directory to networq-web and run command:

```
$ git pull
```

### 2. Update the dependencies using Composer

Within the same networq-web directory run this command:

```
$ composer install # install / update latest dependencies
```
## Updating NetworQ-cli

## 1. Updating networq-cli


Set directory to networq-cli:


```
$ git pull
```
### 2. Update the dependencies using Composer

Within the same networq-cli directory run this command:

```
$ composer install # install / update latest dependencies
```

## Next Steps

<!--- stay DRY where possible, maybe after getting started is approved and proofed copy through? --->

* Follow [2-4](getting-started.md#2-install-networq) of installing networq in getting started.

## Test your success

The end-goal is that you can type `networq` + enter and be presented with something like this:

![cli/Bin Path settings for Windows](/images/CommandsAvailable.PNG) 

"Command not found" suggests that there's still something that needs fixing on the PATH variable, or resetting/reloading the bash session.

## If you relocate networq-cli then update the PATH Environment

### Windows

In the Windows control panel navigate to or search for "advanced system settings"

![PHP Path settings for Windows](/images/PHP_Windows_VariablesSetings.PNG) 

Select "Environment Variables"
Navigate to the path settings for Windows and select "Edit"
If there is an existing PATH for the cli\bin then verify it is correct.
If not select Edit and browse to the correct location.
If there is no current path select "New" and add the path, giving it an appropriate name.

![cli/Bin Path settings for Windows](/images/EditPathforCliBin.PNG) 

After updating your PATH variable, you'll usually need to restart your bash terminal application for the changes to take effect.

### Linux/Mac
