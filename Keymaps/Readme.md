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

```
You will need to install 
	a. MSYS2
	b. Git
	c. Python 3x
	d. QMK CLI
	e. Download QMK tool box
```

Follow the installation instructions on the MSYS2 homepage.

Close any open MSYS terminals and open a new MinGW 64-bit terminal.

> NOTE: This is not the same as the MSYS terminal that opens when installation is completed.

Then, run the following:

```
pacman --needed --noconfirm --disable-download-timeout -S git mingw-w64-x86_64-toolchain mingw-w64-x86_64-python3-pip
python3 -m pip install qmk
```


