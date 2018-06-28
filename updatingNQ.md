
---
draft: True
author: j.faassen@linkorb.com
editor: masterbunny@gmail.com
notes: - This is a working doc.
---

## Updating NetworQ-web

1) Set git bash directory to networq-web:

```
	$ git pull

```

2) Within the same networq-web directory, update the dependencies using Composer:

```
	$ composer install # install / update latest dependencies
```

## Updating NetworQ-cli

1) Set git bash directory to networq-cli:

```
	$ git pull

```

2) Within the same networq-web directory, update the dependencies using Composer:

```
	$ composer install # install / update latest dependencies
```

## Update the PATH Environment

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


The end-goal is that you can type `networq` + enter and be presented with something like this:

https://www.dropbox.com/s/1wsc0x2f0m2h7ru/Screenshot%202018-06-27%2017.36.33.png?dl=0

As long as it says something like "Command not found" there's still something that needs fixing on the PATH variable, or resetting/reloading the bash session.

-----

Next up, `cd` to the repository path of the `holacracy-package`:

    $ cd ~/Documents/GitHub/holacracy-package
    $ networq install

The `networq install` command reads the `package.yaml` from the current directory, and sees what "dependencies" are listed.

For each of the listed dependencies (networq:core and networq:organization in this case) it will try to `git clone` them for you in the current directory + "packages/" sub-directory.

If this command is successful, you'll find a `packages/` directory in your `holacracy-repository`.

If this command is not successful, perhaps it can't properly run `git` from the command-line. Try running `git --help` to check.. if that doesn't work, consult the git windows documentation to see how to make that work.

------

Now we can switch back to `networq-web` and edit the `.env` file.

Edit the NETWORQ_GRAPH line like this:

```ini
NETWORQ_GRAPH=C:\Users\bunny\Documents\GitHub\holacracy-package
NETWORQ_EXAMPLES=true
```

The `NETWORQ_GRAPH` variable tells networq-web to load the main package from your holacracy-package path (and all of it's dependencies, and all of their dependencies, etc).

The `NETWORQ_EXAMPLES=true` line tells networq to load the example nodes in the `examples/` directory of your main package: holacracy-package.

Now start the `networq-web` server again using `php -S localhost:54321 -t public/`

If we're lucky, visiting http://localhost:54321 now shows you a beautiful screen looking something like this:

https://www.dropbox.com/s/k09ywv54drd7jpt/Screenshot%202018-06-27%2017.53.28.png?dl=0


That'd be cool because we can actually get started with the star of the show: NetworQ itself!

If it doesn't work, the demo server https://demo.networq.io/ shows the output that would be expected if everything had worked locally. Maybe still valuable to click around there...

## Next steps

If all of this works, you can try reading/understanding the yaml files in your holacracy-package repository. This is where the "types" are defined. The "examples/" directory contains the actual (example) data that is displayed in the browser.

You could even try editing some of these example nodes (yaml) files to get a feel for it (you can always revert it back from git :-))

Holacracy is just a cool example module implementing ideas from http://holacracy.org/

There are other packages on http://github.com/networq (everything ending in `-package`).

<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).



