# spams-matlab-install-on-win10

My experience to install spams-matlab-v2.6-2017 on Win10 is written down belows for future reference:

step 1) download spams-matlab-v2.6-2017 from official website:http://spams-devel.gforge.inria.fr/downloads.html

step 2) open the compile.m file (e.g.,E:\matlab_repository\toolboxes\spams-matlab-v2.6-2017-02-27\spams-matlab-v2.6), and make following changes: compiler='mex' (orignially compiler='gcc'), use_multithread=false (originally use_multithread=true)

step 3) In Matlab command window, type: 'mex -setup', which is used to check useable C++ compiler. 

In my computer, it has been already installed MinGW64 Compiler (C++), but when i run compile.m with MinGW64 it always reports errors (looks like spams-matlab interface cannot be successfully compiled by MinGW64). Then I download Visual Studio 2017 from this website (for trail): https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2017, and install it on my computer. After that, I run command: mex -setup C++, and select Microsoft Visual C++2017 as the compiler.


