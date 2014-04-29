C++ Starting Kit for Sublime Text
=================================

Go to [The Guide](https://github.com/kodLite/cppStartingKit#the-guide)

## Features
* C, C++ and C++11 combined and improved syntax highlighting support.
* Custom C++ build system for g++ compiler.

**It is highly recommended to read the Philosophy section just below before to install and use this package.**

## Philosophy
The main objective of this project is to **provide a real starting kit for beginners with C++ and Sublime Text** including :
* A syntax definition which gives you the flexibility to make precise customizations to your syntax highlighting.
* An associated theme which includes all the new scopes. (see [Oasis Theme](https://github.com/kodLite/Oasis-Theme))
* An intelligible build system.
* A relevant documentation for a quick start and an accessible maintenance.(see [The Guide](https://github.com/kodLite/cppStartingKit#the-guide))

**I have to mention two major things before to continue :**

* First, **I'm really new in programming**. The first release of this package is the result of my first week of learning. My original goal is to learn C++ with a lightweight and flexible tool. A tool which allow me to customize my environment and let me control things like compiling. This was not an easy task because of the huge amount of solutions available out there. Finally Sublime Text seems to suit pretty well to my needs with his reasonable learning curve. 
* The second thing I want to mention is, in my opinion, **this package is not yet ready for production**. Even if the main behaviors are ever described and seem to work correctly, I think it will demand you a certain investment before to make it fully functional for your professional environment. 

But don't worry, as it is my primary tool for my journey to C++, I will do my best to update it quickly and make it fully functional as soon as possible.

## Preview
**[Oasis Theme](https://github.com/kodLite/Oasis-Theme) not included**

![C++ Starting Kit Standard behavior](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/standard-behavior.jpg?raw=true)

**Arithmetic operators are now customizable.**

![C++ Starting Kit Arithmetic Operators](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/custom-arithmetic-operators.jpg?raw=true)

**More customization.**

![C++ Starting Kit Customize Everything](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/customize-everything.jpg?raw=true)

**Any function support.**

![C++ Starting Kit Any Function Support](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/any-function-detection.jpg?raw=true)

**Easily [add to your syntax definition](https://github.com/kodLite/cppStartingKit#customize-your-syntax-definition) with the [documented configuration file](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage).**

![C++ Starting Kit Add Keyword](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/Namespace-added.jpg?raw=true)

The Guide
=========

If you are new in C++ and you want to use Sublime Text as a small IDE the **C++ Starting Kit** and this guide are for you. 

If you are anyone else you can find tips which will help you to customize your Sublime Text environment.

I made this project because I found really hard to start C++ with Sublime Text. Mainly because the native support is in my sense not really functional, the documentation not design for beginners and informations are rarely complete on forums and other ressources. 

I tried to collect every bit of useful informations from my own experience and centralised it in one major document.

This guide covers the management of this package with Sublime Text 3 under Windows 7 x64. Things are pretty much the same depending on your version of Sublime Text and your operating system. 

The informations provided in this guide should help you to understand the core of the **C++ Starting Kit** and how globally things work inside Sublime Text. 

# Install C++ Starting Kit

### Manually

(To do)

### From Package Control

(To do)


# Customize your color scheme

If you use a default color scheme or something downloaded from the Internet and you want to use the **C++ Starting Kit** you will have to manage your scopes inside your configuration file(`*.tmTheme`).

A recommended alternative is to try the [Oasis Theme](https://github.com/kodLite/Oasis-Theme) especially build for. 

Otherwise check the following, it's a set of useful tips which will help to customize your Sublime Text environment.

### Change your color scheme

* Go to `Preferences > Color Scheme` menu.

### Locate your color scheme configuration file

* Default color schemes are located inside the package `Sublime Text/Packages/Color Scheme - Default.sublime-package`. (see [how to edit a *.sublime package](https://github.com/kodLite/cppStartingKit#how-to-edit-a-sublime-package)) 
* User color schemes are located in `Sublime Text/Data/Packages/User/*.tmTheme`.

If you want to tweak a default color scheme I recommend you to copy it and rename it in your `Sublime Text/Data/Packages/User` folder.

### Find a scope name

* Put your cursor under the scope you want to know the name.
* Type `Ctrl + Alt + Shift + P`.
* The name will appear at the bottom of your Sublime Text interface.

### Search a scope in your color scheme configuration file

* Make a search by typing `Ctrl + F`.
* Type what you want to find and don't forget to look everywhere in the document by pressing `Find` and `Find Prev`.

### Add a missing scope in your color scheme configuration file

If you are sure that the scope doesn't exist in your `*.tmTheme`, which contain your color scheme, add the following lines and fill the fields between the tags(`<tag>Your specification</tag>`) correctly :

		<dict>
			<key>name</key>
			<string>Scope name</string> 		<!-- Enter a name for your scope here. -->
			<key>scope</key>
			<string>Scope definition</string> 	<!-- Enter your scopes here. (ex : keyword.ccpp) -->
			<key>settings</key>
			<dict>
				<key>fontStyle</key>
				<string></string> 				<!-- Choose a style (ex : italic, bold, italic bold) -->
				<key>foreground</key>
				<string></string> 				<!-- Choose a color (ex : #49a629) -->
			</dict>
		</dict>

### C++ Starting Kit scope list

(To do)

#Customize your syntax definition

## What you need to know

### Introduction to CCpp.tmLanguage

The syntax definition(`*.tmLanguage`) allow the syntax highlighting(`*.tmTheme`). Both are part of the **C++ Starting Kit** package.
To be able to quickly get a result, only the necessary pieces of code were modified :
* `C.tmLanguage` and `C++.tmLanguage`, which were mainly responsible of the syntax definition, were merged into [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage).
* `C++.sublime-build`, which embed the build system, was customized and renamed in [`CCpp.sublime-build`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build).
* `C++.sublime-settings`, which specifies the supported file types, was just renamed in [`CCpp.sublime-settings`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-settings). 
* All the other files were preserved.

To keep a flexible and easily maintainable system it was necessary to analyze, cut out and document the original code. Then extract useful pieces, merge them and reorganize the whole. (see [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage))

The greatest part of the changes are in the [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage). Now it is organized and documented to facilitate his approach and his maintenance. Functional pieces like comments, quoted strings or preprocessor modules are untouched.

### Structure of CCpp.tmLanguage

The [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage) file was coded with a very simple logic : a main behavior is establish then small chunks of code were added to improve functionnalities and avoid undesirable behaviors.

For example the curly brackets were defined as `open.curly.bracket.ccpp` and `close.curly.bracket.ccpp`. Then `open.curly.bracket.block.ccpp` and `close.curly.bracket.block.ccpp` were added to override the first definition and define what we could call the "block detection".

If you want to follow this process you have to put the main behavior at the bottom of your overrides, and not the opposite !!! (see the example below)

The entire document is organised like this, everything is documented as possible. This allow you to quickly understand the system and easily add functionalities if necessary.

![C++ Starting Kit Syntax Definition Override](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/overrides.jpg?raw=true)

### How to edit a *.sublime package

`*.sublime-package` like **C++ Starting Kit** are `*.zip` archive. If you want to modify files inside those packages you have to follow these steps :
* Inside your `Sublime Text/Packages` folder you have to find the package you want to modify.
* Copy and paste it in a safe place and do your tweaks on this copy.
* To open the package you have to rename it in `*.zip` then extract it.
* Inside the extracted folder you will find the editable files.
* When finished, save your changes.
* Close Sublime Text. 
* "Re-archive" your extracted folder in `*.zip` then rename it in `*.sublime-package`.
* Copy your updated `*.sublime-package` and overwrite the one in your `Sublime Text/Packages` folder.
* Restart Sublime Text.

# Use the included C++ custom build system

## Prerequisite
If you want to use the **C++ Starting Kit** build system you have 5 things to do :
* Install a compiler compatible with g++. In our case MinGW -64 for x86 and x64 developments.
* Add your compiler to your system path.
* Restart your computer.
* Understand how the build system work.
* Know how to use the build system.

### Install MinGW -64
* Go to the MinGW -64 project homepage at [http://mingw-w64.sourceforge.net/](http://mingw-w64.sourceforge.net/)

This should give you the page below then click on the download page where it is highlighted on the next image. 

![MinGW 64 project main page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-main-page-marked.jpg?raw=true)

* To keep things easy, on the download page, get **the installer**, highlighted on the next image. This should give you a file called `mingw-builds-install.exe`.

![MinGW 64 project download page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-download-page-marked.jpg?raw=true)

* Then launch `mingw-builds-install.exe`. An installation process will begin where you have two major thing to take care of.

You have to remember the path where you will install it because it will be necessary to [add it to your system path](https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path). Otherwise the build system will not recognize the commands invoked by the C++ Starting Kit build systen. I recommend you to install it in a more convenient place like `C:\MinGW\x64` because if you have an other version of MinGW to install you can do it properly just by adding an new folder like `C:\MinGW\x86`.

The second thing is to chosse the correct options for this specific installation. Change the default architecture for the x64 and keep the rest as it is.

![MinGW 64 project options](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-install-options-marked.jpg?raw=true)

* Click `Next` when it's required and let the installation finish is work.
* Now you need to [add MinGW to your system path]((https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path)).

### Add folders to your system path
Add folders to your system path allow programs to invoke specific commands.

In the case of MinGW -64 the command `g++` invoked by the **C++ Starting Kit** build system, which is in reality `g++.exe`, must be indicate to your system to allow Sublime Text to call it when it compile your programs.

* Go to your `Start Menu`.
* Right click on `Computer` then select `Properties`.
* On the left side choose `Advanced system settings`.
* Go to the `Advanced` tab then click on `Envrironment Variables`.
* In `System variables` scroll down until you find `path`.
* Then click edit.

This will give you a list of folders userful for your system to work. Be really vigilant with the content inside this field. I recommend you to copy paste it first(`Ctrl + A`, `Ctrl + C` to copy the entire line then `Ctrl + V` to paste) in a safe document to be able to access it or bring it back to his default state if necessary. 

If you followed this guide from the beginning you have to add at the end of this line a semi colon `;` directly followed by `C:/MinGW/x64/mingw64/bin`.

* Then log off or restart your computer to apply the changes.

### Understand the build system

**The basics**

By default the build system is design as follow :

	{
		"cmd": ["g++", "-Wall","*.cpp", "-I", "../header","-o", "${file_path}/${file_base_name}"],
		"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
		"working_dir": "${file_path}",
		"selector": "source.c++",
		"shell" : true,
	
		"variants":
		[
			{
				"cmd": ["start","cmd", "/k","${file_path}/${file_base_name}"],
				"name": "Run"
			},
		]
	}

I will just detail the first line which are the more important, I recommend you to check the documentation of Sublime Text and MinGW to customize it :

* `"g++"` invoke g++.exe.
* `"-Wall"` will warn you for all errors.
* `"*.cpp"` wil include every `*.cpp` file in the same folder.
* `"-I"` and `"../header"` will include a folder called `header` one level above the current file in your project directory.
* `"-o"` followed by `"${file_path}/${file_base_name}"` will generate an executable "*.exe" in the current file path with your file name as a base.

To `Build` and `Run` the commands are `Ctrl + B` and `Ctrl + Shift + B`.

**Go further**

If you want to test g++ without any Sublime Text build system you can open a command prompt where your main `*.cpp` is stored.

Locate the folder, `Shift + Richt Click`, then choose `Open command window here`.

Then type the following commands which are equivalent to the **C++ Starting Kit** build system : 

`g++ -Wall *.cpp -I ../header -o myProgramName.exe`

As a result you will get a `myProgramName.exe` inside your folder that you can run by typing his name inside the command prompt.

# Sublime Text projects

### Use the build system
* `Ctrl + B` to build your program.
* `Ctrl + Shit + B` to run your program.
