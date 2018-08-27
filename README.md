# spams-matlab-install-on-win10

My experience to install spams-matlab-v2.6-2017 on Win10 is written down belows for future reference:

step 1) download spams-matlab-v2.6-2017 from official website:http://spams-devel.gforge.inria.fr/downloads.html

step 2) open the compile.m file (e.g.,E:\matlab_repository\toolboxes\spams-matlab-v2.6-2017-02-27\spams-matlab-v2.6), and make following changes: compiler='mex' (orignially compiler='gcc'), use_multithread=false (originally use_multithread=true)

step 3) In Matlab command window, type: 'mex -setup', which is used to check useable C++ compiler. 

In my computer, it has been already installed MinGW64 Compiler (C++), but when i run compile.m with MinGW64 it always reports errors (looks like spams-matlab interface cannot be successfully compiled by MinGW64). Then I download Visual Studio 2017 from this website (for trail): https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2017, and install it on my computer. After that, I run command: mex -setup C++, and select Microsoft Visual C++2017 as the compiler.


step 4) Run compiler.m again. But in my experience it has the following error: ".\prox\groups-graph.h(95): error C2039: 'isspace': is not a member of 'std'". Then I solve the problem following website:https://www.jianshu.com/p/9859bd3b7e6d. That is: open the file: prox/groups-graph.h， and change all: std::isspace to isspace.

Luckly no other errors are reported for my installation.
