


1. vs code ## 


1. Install Visual Studio Code.

2. Install the C/C++ extension for VS Code. You can install the C/C++ extension by searching for 'c++' in the Extensions view (Ctrl+Shift+X).



1. https://code.visualstudio.com/docs/cpp/config-mingw

## C:\Program Files (x86)\mingw-w64\i686-8.1.0-posix-dwarf-rt_v6-rev0

If you have Visual Studio or WSL installed, you may need to change compilerPath to match the preferred compiler for your project. For example, if you installed Mingw-w64 version 8.1.0 using the i686 architecture, Win32 threading, and sjlj exception handling install options, the path would look like this: C:\Program Files (x86)\mingw-w64\i686-8.1.0-win32-sjlj-rt_v6-rev0.

Next steps#


## checking::

```c++

Microsoft Windows [Version 10.0.19041.450]
(c) 2020 Microsoft Corporation. All rights reserved.

C:\Users\Taxi>g++ --version
g++ (i686-posix-sjlj-rev0, Built by MinGW-W64 project) 8.1.0
Copyright (C) 2018 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.


C:\Users\Taxi>gdb --version
GNU gdb (GDB) 8.1
Copyright (C) 2018 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "i686-w64-mingw32".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
<http://www.gnu.org/software/gdb/documentation/>.
For help, type "help".
Type "apropos word" to search for commands related to "word".

C:\Users\Taxi>

```



### Now press Ctrl+S to save the file. Notice how the file you just added appears in the File Explorer view (Ctrl+Shift+E) in the side bar of VS Code:



# C:\Users\Taxi\projects\helloworld\.vscode\tasks.json



## Build helloworld.cpp#
### Next, you'll create a tasks.json file to tell VS Code how to build (compile) the program. This task will invoke the g++ compiler to create an executable file based on the source code.

### From the main menu, choose Terminal > Configure Default Build Task. In the dropdown, which will display a tasks dropdown listing various predefined build tasks for C++ compilers. Choose g++.exe build active file, which will build the file that is currently displayed (active) in the editor.


## tasks json::

```json
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "cppbuild",
			"label": "C/C++: g++.exe build active file",
			"command": "C:\\Program Files (x86)\\mingw-w64\\i686-8.1.0-posix-sjlj-rt_v6-rev0\\mingw32\\bin\\g++.exe",
			"args": [
				"-g",
				"${file}",
				"-o",
				"${fileDirname}\\${fileBasenameNoExtension}.exe"
			],
			"options": {
				"cwd": "C:\\Program Files (x86)\\mingw-w64\\i686-8.1.0-posix-sjlj-rt_v6-rev0\\mingw32\\bin"
			},
			"problemMatcher": [
				"$gcc"
			],
			"group": {
				"kind": "build",
				"isDefault": true
			},
			"detail": "compiler: \"C:\\Program Files (x86)\\mingw-w64\\i686-8.1.0-posix-sjlj-rt_v6-rev0\\mingw32\\bin\\g++.exe\""
		}
	]
}
```


Ctrl + Shift + B ::

```c++

> Executing task: C/C++: g++.exe build active file <

Starting build...

Build finished successfully.

Terminal will be reused by tasks, press any key to close it.

> Executing task: C/C++: g++.exe build active file <

Starting build...

Build finished successfully.

Terminal will be reused by tasks, press any key to close it.
```

## complete output::

```json

Type "apropos word" to search for commands related to "word".

C:\Users\Taxi>mkdir projects

C:\Users\Taxi>cd projects

C:\Users\Taxi\projects>mkdir helloworld

C:\Users\Taxi\projects>cd helloworld

C:\Users\Taxi\projects\helloworld>code .

C:\Users\Taxi\projects\helloworld>dir
 Volume in drive C has no label.
 Volume Serial Number is A4D4-418F

 Directory of C:\Users\Taxi\projects\helloworld

11/14/2020  06:20 AM    <DIR>          .
11/14/2020  06:20 AM    <DIR>          ..
11/14/2020  06:17 AM    <DIR>          .vscode
11/14/2020  06:20 AM               303 1stCProgramVSCodeMinGWCompiler.cpp
11/14/2020  06:20 AM           158,008 1stCProgramVSCodeMinGWCompiler.exe
               2 File(s)        158,311 bytes
               3 Dir(s)  93,753,790,464 bytes free

C:\Users\Taxi\projects\helloworld>1stCProgramVSCodeMinGWCompiler.exe
HelloXXXXX C++XXXXX WorldXXXXX fromXXXXX VS CodeXXXXX and the C++ extension!XXXXX

C:\Users\Taxi\projects\helloworld>
```