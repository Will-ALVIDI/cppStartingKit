C++ Starting Kit for Sublime Text
=================================
## Features
* C, C++ and C++11 combined and improved syntax highlighting support.
* Custom C++ build system for g++ compiler.

**It is highly recommended to read the [Philosophy](https://github.com/kodLite/cppStartingKit#philosophy) and the [Guide](https://github.com/kodLite/cppStartingKit#the-guide) before to install and use this package.**

## Philosophy
The main objective of this project is to **provide a complete starting kit for beginners with C++ and Sublime Text** including :
* A syntax definition which gives you the flexibility to make precise customizations to your syntax highlighting. (see the [Preview](https://github.com/kodLite/cppStartingKit#preview) of the **C++ Starting Kit**)
* An associated theme which includes all the new scopes. (see [Oasis Theme](https://github.com/kodLite/Oasis-Theme))
* An intelligible build system. (see the [C++ Starting Kit build system](https://github.com/kodLite/cppStartingKit#use-the-c-starting-kit-build-system))
* A relevant documentation for a quick start and an accessible maintenance.(see [The Guide](https://github.com/kodLite/cppStartingKit#the-guide))

**I have to mention two major things before to continue :**

* First, **I'm really new in programming**. The first release of this package is the result of my first week of learning. My original goal is to learn C++ with a lightweight and flexible tool. A tool which allow me to customize my environment and let me control things like compiling.
* The second thing I want to mention is, in my opinion, **this package is not yet ready for production**. Even if the main behaviors are ever described and seem to work correctly, I think it will demand you a certain investment before to make it fully functional for your an advanced or professional usage. 

As it is my primary tool for my learning of C++ I will do my best to make it fully functional as soon as possible.

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

I made this project because I found really hard to start C++ with Sublime Text. Mainly because the native support is, in my opinion, not really functional, the documentation not design for beginners and too many things are involved and are not entirely covered by forums and other ressources. 

I tried to collect every bit of useful informations from my own experience and centralised it in this document.

This guide covers the key points to start using Sublime Text 3 for C++ under Windows 7 x64. Things are pretty much the same depending on your version of Sublime Text and your operating system. 

The informations provided in this guide should help you to understand the core of the **C++ Starting Kit** and how globally things work inside Sublime Text. 

# Install C++ Starting Kit

### Manually

(To do)

### From Package Control

(To do)

#Customize your syntax definition

## What you need to know

### Introduction

`*.sublime-package` inside your `Sublime Text/Packages` folder contains specific language definitions as well as default theme(`Theme - Default.sublime-package`) and default color schemes(`Color Scheme - Default.sublime-package`).

Languages are mainly define by a configuration file, `*.tmLanguage`, inside those `*.sublime-package`. (see [how to edit a *.sublime package](https://github.com/kodLite/cppStartingKit#how-to-edit-a-sublime-package))

### Global Structure of CCpp.tmLanguage

To get a quick result in the **C++ Starting Kit** development only the necessary changes were made :
* `C.tmLanguage` and `C++.tmLanguage`, which were mainly responsible of the syntax definition, were merged into [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage).
* `C++.sublime-build`, which embed the build system, was customized and renamed in [`CCpp.sublime-build`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build).
* `C++.sublime-settings`, which specifies the supported file types, was just renamed in [`CCpp.sublime-settings`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-settings). 
* All the other files were preserved.

To keep a flexible and easily maintainable system it was necessary to analyze, cut out and document the original code. Then extract useful pieces, merge them and reorganize the whole. (see [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage))

The greatest part of the changes are in the [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage). Now it is organized and documented to facilitate his approach and his maintenance. Functional pieces like comments, quoted strings or preprocessor modules are untouched.

### Logic of CCpp.tmLanguage

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

**Arithmetic operators**(keyword.operator.arithmetic.ccpp), **Brackets**(open.curly.bracket.ccpp, close.curly.bracket.ccpp,open.round.bracket.ccpp, close.round.bracket.ccpp, open.angle.bracket.ccpp, close.angle.bracket.ccpp, open.curly.bracket.ovr.ccpp, close.curly.bracket.ovr.ccpp), **Block brackets**(open.curly.bracket.block.ccpp, close.curly.bracket.block.ccpp), **Punctuation**(period.ccpp, coma.ccpp,semi_colon.ccpp), **End of line semi colon**(semi_colon.eol.ccpp), **Function support**(function.support.ccpp) 

# Use the C++ Starting Kit build system

## Prerequisite
If you want to use the **C++ Starting Kit** build system you have 5 things to do :
* Install a compiler compatible with g++. In our case MinGW -64 for x86 and x64 developments.
* Add your compiler to your system path.
* Restart your computer.
* Understand how the build system work.
* Know how to use the build system.

### Install MinGW-w64
* Go to the MinGW-w64 project homepage at [http://mingw-w64.sourceforge.net/](http://mingw-w64.sourceforge.net/)

This should give you the page below then click on the download page highlighted on the next image. 

![MinGW-w64 project main page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-main-page-marked.jpg?raw=true)

* To keep things easy, on the download page, get **the installer**, highlighted on the next image. This should give you a file called `mingw-builds-install.exe`.

![MinGW-w64 project download page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-download-page-marked.jpg?raw=true)

* Then launch `mingw-builds-install.exe`. An installation process will begin where you have two major thing to take care of.

You have to remember the path where you will install it because it will be necessary to [add it to your system path](https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path). Otherwise the build system will not recognize the commands invoked by the **C++ Starting Kit build system**. I recommend you to install it in a more convenient place like `C:\MinGW\x64` because if you have an other version of MinGW to install you can do it properly just by adding a new folder like `C:\MinGW\x86`.

The second thing is to chosse the correct options for this specific installation. Change the default architecture for the x64 and keep the rest as it is.

![MinGW-w64 project options](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-install-options-marked.jpg?raw=true)

* Click `Next` when it's required and let the installation finish is work.
* Now you need to [add MinGW-w64 to your system path]((https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path)).

### Add folders to your system path
Add folders to your system path allow programs to invoke specific commands.

In the case of MinGW-w64 the command `g++` invoked by the **C++ Starting Kit** build system, which is in reality `g++.exe`, must be indicate to your system to allow Sublime Text to call it when it compile your programs.

* Go to your `Start Menu`.
* Right click on `Computer` then select `Properties`.
* On the left side choose `Advanced system settings`.
* Go to the `Advanced` tab then click on `Envrironment Variables`.
* In `System variables` scroll down until you find `path`.
* Then click edit.

This will give you a list of folders useful for your system to work. Be really vigilant with the content inside this field. I recommend you to copy paste it first(`Ctrl + A`, to select everything, `Ctrl + C` to copy what is selected then `Ctrl + V` to paste) in a safe document to be able to access it or bring it back to his default state if necessary. 

If you followed this guide from the beginning you have to add at the end of this line, inside the field, a semi colon `;` directly followed by `C:/MinGW/x64/mingw64/bin`.

* Then log off or restart your computer to apply the changes.

### Understand the C++ Starting Kit build system

**Introduction**

Build systems in Sublime Text are project specific. It is hard to make one which covers every type of project you will do. The **C++ Starting Kit** provides a build system and the following documentation as a starting point, not as an universal solution.

I recommend you to create your own first build system inside the user folder in Sublime Text :

* Go to `Sublime Text/Data/Packages/User` folder.
* Or from Sublime Text by going to `Preferences > Browse Packages...` then go inside the `User` folder. 
* Create a file with an easily recognizable name like `User - C++.sublime-build`.
* Copy and paste the following, it is a copy of the **C++ Starting Kit** build system :

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

* Then activate your custom build system by going, in this case, to `Tools > Build System > User - C++`.

I will just detail the first lines which are the most important.

* `"g++"` invoke g++.exe, the compiler.
* `"-Wall"` will warn you for all errors.
* `"*.cpp"` wil include all the `*.cpp` files stored in the same folder.
* `"-I"` and `"../header"` will include a folder called `header` one level above the current file in your project directory.
* `"-o"` followed by `"${file_path}/${file_base_name}"` will generate an executable, a `*.exe` file, inside the current file path with your file name as a base.

**Build and Run by a command prompt**

The commands inside the `C++ Starting Kit` are reproducible and testable inside a command prompt. Test your Sublime Text build systems this way before to adapt it for Sublime Text build system.

Few steps are necessary to do it :
* Locate the folder where you main program is stored, press `Shift + Richt Click` then choose `Open command window here`. This will open a command prompt ready to work directly on you project directory and avoid you to do this manipulation by command line.
* Then type the following commands which are equivalent to the **C++ Starting Kit** build system : 

`g++ -Wall *.cpp -I ../header -o myProgramName.exe`

As a result you will get a `myProgramName.exe` file inside your folder and you can run it by typing his name inside the command prompt then press `Enter`.

### Use the C++ Starting Kit build system

Default commands for `Build` and `Run` with C++ Starting Kit build system are :
* `Ctrl + B` to build your program.
* `Ctrl + Shit + B` to run your program.

# Sublime Text projects

# Go further
