# Flashing lily58 Pro

Since lily is a split keyboard both half of the PCB have a pro micro and any one of them can become a master.

But it is common \ recommended to have the left one as the master.

1. Go to this link [QMK](https://config.qmk.fm/).

```
	a. Choose  the lily58/rev1 as the keyboard from the drop-down menu

	b. Just drag and drop to re-arrange the keys as desired.

	c. Once you are happy with the arrangement of the keys click on compile on the top right corner.

	d. Next click on the download symbol to Export the QMK JSON file.
```


2. Setting up QMK environment


You will need to install 

[MSYS2](http://www.msys2.org/)

[Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

[Python 3x](https://www.python.org/downloads/)

[QMK CLI](https://beta.docs.qmk.fm/tutorial/newbs_getting_started)

[QMK tool box](https://qmk.fm/toolbox/)


Follow the installation instructions on the MSYS2 homepage.

Close any open MSYS terminals and open a new MinGW 64-bit terminal.

> NOTE: This is not the same as the MSYS terminal that opens when the installation is completed.

Then, run the following:

> Note: You can create a new profile or just edit some existing profiles.

Once all the environment 

Navigate to the folder where you have downloaded the JSON file from qmk config

and execute the command

```
qmk json2c <json_file>
```

This generates an output with the keymaps configurations copy this to the clipboard

Next, navigate to 

```
qmk_firmware/keyboards/lily58/keymaps/default
```

Now open the file keymap.c and replace the keymap configurations with the output new keymaps copied to the clipboard

repplace the const variable [here!][https://github.com/santoshmn26/Lilypro58-build-log/blob/master/Keymaps/default/keymap.c#L30].

Next, save the file and exit

Next, execute the following commands to generate a hex file 

```
qmk compile -km default
qmk compile -kb default
```

Next, open the qmk toolbox

```
1. Browse to the hex file location 
2. Select the pro micro used in the keyboard it is usually atmega32u4
3. Click on the reset button on the left PCB (Master side)
4. Click on Flash
```


## All Done!! Enjoy your lily!
