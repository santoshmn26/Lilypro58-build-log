# Flashing lily

Since lily is a split keyboard its and both the split pcb's have a pro micro any one of them can become a mster.

But it is common \ recommended to have the left one as the master.

1.Go to this link [QMK](https://config.qmk.fm/).

```
	a. Choose  the lily58/rev1 as the keyboard from the drop down menu

	b. Just drag and drop to re-arrange the keys as desired.

	c. Once you are happy with the arrengement of the keys click on compile on the top right corner.

	d. Next click on the download symbol to Export the QMK json file.
```


2. Setting up QMK environment


You will need to install 

[MSYS2](http://www.msys2.org/)

[Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

[Python 3x](https://www.python.org/downloads/)

[QMK CLI](https://beta.docs.qmk.fm/tutorial/newbs_getting_started)

[Download QMK tool box](https://qmk.fm/toolbox/)


Follow the installation instructions on the MSYS2 homepage.

Close any open MSYS terminals and open a new MinGW 64-bit terminal.

> NOTE: This is not the same as the MSYS terminal that opens when installation is completed.

Then, run the following:

> Note: You can create a new profile or just edit some existing profiles.

Once all the environment is setup navigate to the folder 

Navigate to the folder where you have downloaded the json file from qmk config

and execute the command

```
qmk json2c <json_file>
```

This generate a output with the keymaps configurations copy this to the clip board

Next navigate to 

```
qmk_firmware/keyboards/lily58/keymaps/default
```

Now open the file keymap.c and replace the keymap configurations with the output new keymaps copied to the clip board

Next save the file and exit

Next execute the following commands to generate a hex file 

```
qmk compile -km default
qmk compile -kb default
```

Next open the qmk toolbox

```
1. Browse to the hex file location 
2. Select the pro micro used in the keyboard it is usually atmega32u4
3. Click on the reset button on the left pcb (Master side)
4. Click on Flash
```

