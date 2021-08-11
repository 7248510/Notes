# Command line notes

# Goal:
Document command line tips/create an easy reference manual.

## Compiling/Interpreting Languages:
* Python = python fileName.py
* Golang = go run .     Multiple go files example = foo.go, bar.go
* Golang build = go build .     This will build a single executable from the multiple go files
* C/C++ = cl fileName.c or cl fileName.cc     This requires visual Studio
* C/C++ = gcc fileName.c or g++ fileName.cc     This requires GCC/G++
* Node = node fileName

#### These are some tips/commands for Programming without an IDE.

## C/C++(Windows):
If you're using Visual Studio's GUI or Build Tools a command prompt will come with your install.<br>Visual Studio Code has an integrated terminal. Unfortunately Atom, Sublime, VI and Nano do not. (If you're on Linux You can split the terminals with TMUX) If your using MinGW GCC/G++ should already be added to your path.<br>In order to use cl and other Visual Studio tools you have to launch the "Developer command prompt"; In order to use this practically(Change the start location so it does not start in your installation folder)Search "Developer Command Prompt" right click "open file location" and copy the short cut to a folder of your choice.<br>Edit the shortcut, right click -> properties and change the "Start in:" field. When you launch the shortcut it will navigate to the folder you input.

### C/C++ Libraries without Visual Studio the example is Libsodium(The example is in Crypto)
## The process is generally the same with C++ Libraries
0. Verify the library(Like Pip & NPM check if the package is malicious)
1. Install VCPKG = git clone https://github.com/Microsoft/vcpkg.git
2. cd vcpkg
2. bootstrap-vcpkg.bat
3. vcpkg install packageName
4. vcpkg integrate install(This is for the GUI)
5. Copy the folder "C:\vcpkg\packages\designated library"
6. Look at the directory structure. For LibSodium I needed the dll to run the file(Dynamically linked), the include directory and the library location to compile the file.
7. Compile(This may take some trouble shooting but I have Examples of Boost, Libsodium and  MySQL(Drivers)
8. Here's an example of compiling Boost
"cl /EHsc /I C:\boost_1_75_0\ -D _WIN32_WINNT=0x0601 boostHttp.cc /link /LIBPATH:C:\boost_1_75_0\stage\lib"
9. Here's an example of LibSodium "cl /EHsc /sdl /W4 libsodium.c /H:\Code\Github\Crypto\crypto\sodium\libsodium_x86-windows\include /link H:\Code\Github\Crypto\crypto\sodium\libsodium_x86-windows\lib\libsodium.lib"

### Resources:
* MSDN
* Github
* Stackoverflow
* Programming Libraries documentation
* [CL Command line files](https://docs.microsoft.com/en-us/cpp/build/reference/cl-command-files?view=msvc-160)
* [Compiler Command Line syntax](https://docs.microsoft.com/en-us/cpp/build/reference/compiler-command-line-syntax?view=msvc-160)

## Linux commands:
* cd /folderName/ = Change the given directory
* cd ../ = Traverse down one directory(go back one directory)
* ls = list the directory contents
* ls -l = list the directory contents, date created, permissions and privileges
* pwd = print working directory
* whoami = output the current users name
* sudo = run a command with elevated access
* uname = OS system
* uname -a = Will list more specific Linux information
* man commandName = will list the manual for a linux command
* echo = message
* cat = view file contents
* grep = parse/sort through data(echo "Hello this is notes" | grep notes) This will highlight notes(depending on the terminal)
* ssh userName@ip = connect to an ssh instance with the Linux user's username
* ip a = view IP information(I recommend this over ifconfig to view information. ifconfig is not on every linux system)
* nmtui(GUI to manage network adapters on CentOS)
* clear = will clear the terminal window
* systemctl COMMAND(start, stop, enable, status) serviceName
* locate fileName(this needs to be installed)
* curl option(The most basic would be curl https://www.google.com/ this will display Google's html)
