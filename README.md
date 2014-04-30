C++ Starting Kit for Sublime Text
=================================
## Features
* C, C++ and C++11 combined and improved syntax highlighting support.
* Custom C++ build system for g++ compiler.

**It is highly recommended to read the [Philosophy](https://github.com/kodLite/cppStartingKit#philosophy) and the [Guide](https://github.com/kodLite/cppStartingKit#the-guide) before to install and use this package.**

## Philosophy
The main objective of this project is to **provide a complete starting kit and starting point for beginners with C++ and Sublime Text** including :
* A syntax definition which gives you the flexibility to make precise customizations to your syntax highlighting. (see the [Preview](https://github.com/kodLite/cppStartingKit#preview))
* An associated theme which includes all the new scopes. (see [Oasis Theme](https://github.com/kodLite/Oasis-Theme))
* An intelligible build system. (see the [C++ Starting Kit build system](https://github.com/kodLite/cppStartingKit#use-the-c-starting-kit-build-system))
* A relevant documentation for a quick start and an accessible maintenance.(see [The Guide](https://github.com/kodLite/cppStartingKit#the-guide))

**I have to mention two major things before to continue :**

* First, **I'm really new in programming**. The first release of this package is the result of my first week of learning. My original goal is to learn C++ with a lightweight and flexible tool. A tool which allow me to customize my environment and let me control things like compiling.
* The second thing I want to mention is, in my opinion, **this package is not yet ready for production**. Even if the main behaviors are ever described and seem to work correctly, I think it will demand you a certain investment before to make it fully functional for an advanced or professional usage. 

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

This guide is designed for people who are really new in C++ programming and want to use Sublime Text as a small IDE. If you follow these instructions step by step you will get crucial informations about Sublime Text environment, the **C++ Starting Kit** and a real starting point for your C++ projects.

If you are anyone else you can find tips to customize your Sublime Text environment for C++ or else.

This guide covers the key points to start using Sublime Text 3 for C++ projects under Windows 7 x64. Things are pretty much the same depending on your version of Sublime Text and your operating system. 

The informations provided in this guide should help you to understand the core of the **C++ Starting Kit** and how globally things work inside Sublime Text. 

I created this project because as a beginner in programming I needed a digestible and intelligible tool and documentation to begin my learning of C++. The native support is, in my opinion, not really functional, the documentation is not designed for beginners and too many things are interlocked and covered with difficulties by forums and other ressources. 

I hope you will find relevant informations to suit to your needs.

# Install Python

### Why Python is necessary

Sublime Text 2 is based on [Python 2.6](https://www.python.org/downloads/)(also compatible with higher versions but inferior to the version 3) and Sublime Text 3 on [Python 3](https://www.python.org/downloads/)(or more).

By default Python is not installed on Windows systems and if you want to take the best of Sublime Text, especially the plugin packages which are the core of this application, you need to have the right dedicated version of Python installed.

To make it functional you have to :

* [Download](https://www.python.org/downloads/) the appropriate version of Python depending of your Sublime Text version.

You can have multiple versions of Python installed.

* Add Python to your system path.

Read entirely this section to [add folders to your system path](https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path) which covers how to add MinGW-w64 to your system path then and adapt it for your Python installation. 

The path you will have to add at the end of the process is the main directory of your Python installation, where the `python.exe` file is stored.

* Then log off or restart your computer to apply the changes.

# Use the C++ Starting Kit build system

## Prerequisite
If you want to use the **C++ Starting Kit** build system to compile your C++ programs inside Sublime Text you will need to combine 5 elements :
* Install a compiler compatible with g++. In our case MinGW-w64 for x86 and x64 developments.
* [Add your compiler to your system path](https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path).
* Restart your computer.
* [Understand how the build system work](https://github.com/kodLite/cppStartingKit#understand-the-c-starting-kit-build-system).
* [Know how to use the build system](https://github.com/kodLite/cppStartingKit#use-the-c-starting-kit-build-system-1).

### Install MinGW-w64
* Go to the MinGW-w64 project homepage at [http://mingw-w64.sourceforge.net/](http://mingw-w64.sourceforge.net/)

This should give you the page below then click on the download page highlighted on the next image. 

![MinGW-w64 project main page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-main-page-marked.jpg?raw=true)

* To keep things easy, on the download page, get **the installer**, highlighted on the next image. This should give you a file called `mingw-builds-install.exe`.

![MinGW-w64 project download page](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-download-page-marked.jpg?raw=true)

* Then launch `mingw-builds-install.exe`. An installation process will begin where you have two major things to take care of.

The first thing is to chosse the correct options for this specific installation. Change the default architecture for the x64 and keep the rest as it is. Then click on the `Next` button.

![MinGW-w64 project options](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/mingw-install-options-marked.jpg?raw=true)

For the next installation sequence you have to remember the path where you will install MinGW-w64 because it will be necessary for the next step. I recommend you to install it in a more convenient place like `C:\MinGW\x64` because you may have later to install a different version of MinGW and you can do it properly just by adding a new folder like `C:\MinGW\x86` for example.

* Then click on the `Next` button and let the installation finish his work.
* Now you need to [add MinGW-w64 to your system path]((https://github.com/kodLite/cppStartingKit#add-folders-to-your-system-path)).

### Add folders to your system path

**As this part is useful for Python installation too, you can [click here](https://github.com/kodLite/cppStartingKit#install-python) to go back to Python section.**

Add folders to your system path allow your system to share programs which can be call by other programs.

The command `g++`, which is in reality the `g++.exe` file stored in your `MinGW-w64/bin`folder, is required by the **C++ Starting Kit** build system and must be available in your system path to allow Sublime Text to access it. To do it just follow these steps :

* Go to your `Start Menu`.
* Right click on `Computer` then select `Properties`.
* On the left side choose `Advanced system settings`.
* Go to the `Advanced` tab then click on `Envrironment Variables`.
* In `System variables` scroll down until you find `path`, select it.
* Then click on the `Edit` button.

This will give you a list of vital folders for your system. Be really vigilant with the content inside this field. I recommend you to copy paste it first(`Ctrl + A`, to select everything, `Ctrl + C`, to copy what is selected, then `Ctrl + V` to paste what you have copied) in a new document in a safe place, that way you can bring everything back to his default state if necessary. 

If you followed this guide from the beginning you have to add at the end of your system path, inside the field, a semi colon `;` directly followed by `C:/MinGW/x64/mingw64/bin`.

* Then log off or restart your computer to apply the changes.

### Understand the C++ Starting Kit build system

**Introduction**

Build systems in Sublime Text are project specific. It is hard to make one which covers every types of projects you will encounter. The **C++ Starting Kit** build system and the following documentation are an introduction and a starting point for your own future sublime build systems.

I recommend you to create your first user build system inside the user folder in Sublime Text :

* Go to `Sublime Text/Data/Packages/User` folder.
* Or from Sublime Text by going to `Preferences > Browse Packages...` then go inside the `User` folder. 
* Create a file with an easily recognizable name like `User - C++.sublime-build`.
* Copy and paste the following. It is a copy of the **C++ Starting Kit** build system :

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

* Save the changes.
* Then activate this custom build system by going in `Tools > Build System` menu and choose your new `User - C++` build system.

The first part of this build system which begin by `"cmd"` is the `Build` function. The second, from `"variants"`, define the `Run` function.

As the compiling processes could require an entire guide I will just detail the first line which is the most important and redirect you to the [MinGW-w64 official documentation](http://www.mingw.org/wiki) and the [Unofficial Sublime Text Documentation](http://sublime-text-unofficial-documentation.readthedocs.org/en/latest/reference/build_systems.html) to improve your knowledges :

* `"g++"` call the launching of `g++.exe`, the compiler.
* `"-Wall"`, for "warn all", will warn you for all errors.
* `"*.cpp"` wil include all the `*.cpp` files stored in the same folder.
* `"-I"`, for "include", and `"../header"` will include a folder called "header", one level above the current file directory.
* `"-o"`, for "output", followed by `"${file_path}/${file_base_name}"` will output your executable, a `*.exe` file, inside the current file path with your current file name as base name.


**Best practices : test your build systems by the command prompt**

The commands inside the **C++ Starting Kit** build system are reproducible and testable inside Windows and his command prompt. Test your Sublime Text build systems this way before to adapt it for Sublime Text build systems.

Few steps are necessary to do it :
* Locate the folder where your main program is stored.
* Press `Shift + Richt Click` then choose `Open command window here`. This will open a command prompt ready to work directly on your project directory and avoid you to do this manipulation by command lines.
* Then try the following commands which are equivalent to the **C++ Starting Kit** build system : 

	**`g++ -Wall *.cpp -I ../header -o myProgramName.exe`**

If you build a program with those commands you will get as a result a `myProgramName.exe` file inside your folder that you can `Run` by typing his name inside the command prompt then pressing `Enter` or by a double click on the file inside your working directory.

### Use the C++ Starting Kit build system

Default commands for `Build` and `Run` with **C++ Starting Kit** build system are :
* `Ctrl + B` to build your program.
* `Ctrl + Shit + B` to run your program.

# Install C++ Starting Kit

### Manually

(To do)

### From Package Control

(To do)

# Customize your color scheme

If you use a default color scheme or something downloaded from the Internet you will have to add [**C++ Starting Kit** scopes](https://github.com/kodLite/cppStartingKit#c-starting-kit-scope-list) inside your `*.tmTheme` configuration file.

A recommended alternative is to try the [Oasis Theme](https://github.com/kodLite/Oasis-Theme) especially build for. 

Otherwise you can take a look to the following. The next part is design as set of useful tips to customize your Sublime Text environment.

### Locate your color scheme configuration file

* Default color schemes are located inside the `Sublime Text/Packages` folder in a file called `Color Scheme - Default.sublime-package`. (see [how to edit a *.sublime package](https://github.com/kodLite/cppStartingKit#how-to-edit-a-sublime-package)) 
* User color schemes are located in `Sublime Text/Data/Packages/User` folder as a `*.tmTheme` file.

If you want to tweak a default color scheme I recommend you to copy and rename it in your `Sublime Text/Data/Packages/User` folder.

### Change your color scheme

* Go to `Preferences > Color Scheme` menu then make your choice between `Color Scheme - Default` and `User` color schemes if you have one.

### Find a scope name

* Put your cursor under the scope you want to know the name.
* Type `Ctrl + Alt + Shift + P`.
* The name will appear at the bottom of your Sublime Text interface.

### Search a scope in your color scheme configuration file

* Make a search by typing `Ctrl + F`.
* Type what you want to find and don't forget to look everywhere in the document by pressing `Find` and `Find Prev`.

### Add a missing scope in your color scheme configuration file

If you are sure that a scope is missing in your `*.tmTheme` file, which contain your color scheme, add the following lines and fill corretly the fields between the tags(`<tag>Your specification</tag>`) :

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

#Customize your syntax definition

## What you need to know

### Introduction

`*.sublime-package` inside your `Sublime Text/Packages` folder contains specific default languages definitions as well as the default theme, `Theme - Default.sublime-package`, and the default color schemes, `Color Scheme - Default.sublime-package`.

Syntax definitions are mainly define by a configuration file, `*.tmLanguage`, inside those `*.sublime-package`.

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

### Global Structure of CCpp.tmLanguage

The `CCpp.tmLanguage` file is the syntax definition included in the **C++ Starting Kit** package.

It is based on the default `C++.sublime-package` file and tweaked as follow :

* `C.tmLanguage` and `C++.tmLanguage`, which were mainly responsible of the syntax definition for the default C and C++ language support, were splitted, documented, merged and improved in [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage).
* `C++.sublime-build`, which embedded the default build system for C and C++, was customized and renamed in [`CCpp.sublime-build`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-build).
* `C++.sublime-settings`, which specifies the supported file types, was just renamed in [`CCpp.sublime-settings`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.sublime-settings). 
* All the other files were preserved.

### Logic behind CCpp.tmLanguage

The [`CCpp.tmLanguage`](https://github.com/kodLite/cppStartingKit/blob/master/CCpp.tmLanguage) file was coded with a very simple logic : a main behavior is establish then small chunks of code were added to improve functionnalities and avoid undesirable behaviors.

For example the curly brackets were defined as `open.curly.bracket.ccpp` and `close.curly.bracket.ccpp`. Then `open.curly.bracket.block.ccpp` and `close.curly.bracket.block.ccpp` were added to override this first definition and define what we could call the curly brackets "block detection". After tests it seems that few exceptions appears and they are corrected by adding an additional code layer.   

![C++ Starting Kit logic](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/logic-ccpp-illustrated.jpg?raw=true)

If you want to follow this process you have to put your main behaviors at the bottom and override them to the top, and not the opposite. (see the example below)

![C++ Starting Kit Syntax Definition Override](https://github.com/kodLite/cppStartingKit/blob/master/screenshot/overrides.jpg?raw=true)

The main idea behind this process is to have a flexbible and easily manageable and maintainable system which allow improvements without breaking everything. 

# Going further

### Sublime Text project management

To learn about Sublime Text project management I recommend you [this tutorial](http://www.youtube.com/watch?v=Kr5ztsD3Yr4) which is a bit longer than other videos available in the Internet but it covers all the basics and necessary tips to a good start with this tool.

### Plugins
Plugin management is the core of Sublime Text and I definitely recommend you to visit regularly [Package Control - Official Website](https://sublime.wbond.net/) to discover, test and contribute to amazing projects and packages provided by the community. 

### Regular expressions

If you want to go further with your syntax definition I can recommend you 3 ressources which were useful for me for the development of **C++ Starting Kit** :
* [Themeforest - Community blog](http://blog.themeforest.net/screencasts/regular-expressions-for-dummies/)
* [RegExr by gSkinner](http://www.regexr.com/v1/)
* [Regular-expressions.info](http://www.regular-expressions.info/)
