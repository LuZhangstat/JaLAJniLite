
<b>JaLAJniLite</b> is a JAVA package providing a java interface for lapack and blas library.


Installing
----------
Go to the folder src/JaLAJniLite, find Makefile, and then run "make". Type "make clean" if you want to clean the generated files. Notice that you may have to change the extension of generated libraries in the Makefile base on your operating system. In OS X you have to change all the extentions of dynamic library to .dylib while in linux the corresponding extensions are .so or .a.

Running the tests
-----------------
For testing, change directory to projects/jama_jni_tests, then type “make” to run test files. If you want to clean testing results and all class files, type "make clean".  


Notes
---------

This packages is intended for some basic problems we encounter when solving linear algebra problems. So we only include several most basic and widely used routines of the blas and lapack library.


Source Repository
-----------------
JaLAJniLite's source-code repository is hosted here on GitHub.


Authors
---------
* Lu Zhang           Department of Biostatistics  UCLA
* LiZhen Nie         ??? 
* Sudipto Banerjee   Department of Biostatistics  UCLA


Licensing
---------
?


