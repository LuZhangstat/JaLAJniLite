
<b>JaLAJniLite</b> is a JAVA package providing a java interface for lapack and blas library.


Build Instructions
------------------

* JaLAJniLite requires the installation of lapack and blas. 

* To compile the package, go to the folder src/JaLAJniLite, find the Makefile and run "make" on the command line. Notice that you may have to change the extension of generated libraries in the Makefile base on your operating system. On OS X you have to change all the extensions of dynamic library to .dylib while on Linux the corresponding extensions are .so or .a. 

* To clean generated file, type “make clean” on the command line. 


Running the tests
-----------------
For testing, change directory to test/JaLAJniLite_tests, then type “make” to run the test files. If you want to clean testing results and all class files, type "make clean".  


Notes
---------
This package is intended for some basic problems we encounter when solving linear algebra problems. So we only include several most basic and widely used routines of the blas and lapack library.


Source Repository
-----------------
JaLAJniLite's source-code repository is hosted here on GitHub.


Authors
---------
* Lu Zhang           Department of Biostatistics  UCLA
* LiZhen Nie         Department of Statistics     Chicago University
* Sudipto Banerjee   Department of Biostatistics  UCLA


Licensing
---------
JaLAJniLite is licensed under the Creative Commons Attribution License. 



