DEST = .
CC = gcc
CFLAGS = $(INCLUDE) $(LIB) 

JAVA_HOME = ../..
JAVA_PACKAGES = $(JAVA_HOME)/packages
JAVA_LIB = $(JAVA_HOME)/lib

JNI_LAPACK_SRC = $(JAVA_HOME)/src/JaLAJniLite/jni_lapack
JNI_BLAS_SRC = $(JAVA_HOME)/src/JaLAJniLite/jni_blas

INCLUDE = -I$(JNI_BLAS_SRC)/c/include \
	-I$(JAVA_HOME)/include \
	-I$(JNI_LAPACK_SRC)/c/include
LIB = -L/usr/local/lib -L$(JAVA_LIB)
C_SRC_LAPACK = $(JNI_LAPACK_SRC)/c/jniLAPACK.c
C_SRC_BLAS = $(JNI_BLAS_SRC)/c/jniCBLAS.c
DYLIB_LAPACK = $(JAVA_HOME)/lib/liblapack_lite.dylib
DYLIB_BLAS = $(JAVA_HOME)/lib/libblas_lite.dylib
	

# For package JaLAJniLite
JC = javac
JH = javah
JFLAGS = -d
JAVA_SRC = $(JNI_LAPACK_SRC)/java/jniLAPACK.java $(JNI_BLAS_SRC)/java/jniCBLAS.java
PACKAGE = $(JAVA_PACKAGES)/JaLAJniLite
HEADER_LAPACK = $(JNI_LAPACK_SRC)/c/include/jniLAPACK.h
HEADER_BLAS = $(JNI_BLAS_SRC)/c/include/jniCBLAS.h

# header file jniLAPACKE.h


all: $(PACKAGE) $(HEADER_LAPACK) $(HEADER_BLAS) $(DYLIB_LAPACK) $(DYLIB_BLAS)

$(PACKAGE): $(JAVA_SRC) 
	$(JC) $(JFLAGS) $(JAVA_PACKAGES) $(JAVA_SRC)

$(HEADER_LAPACK): 
	$(JH) -o $(HEADER_LAPACK) -classpath $(JAVA_PACKAGES) JaLAJniLite.jni_lapack.jniLAPACK 

$(HEADER_BLAS):
	$(JH) -o $(HEADER_BLAS) -classpath $(JAVA_PACKAGES) JaLAJniLite.jni_blas.jniCBLAS

$(DYLIB_LAPACK): $(C_SRC_LAPACK)
	$(CC) $(CFLAGS) -shared -fPIC $(C_SRC_LAPACK) -llapack -o $(DYLIB_LAPACK)

$(DYLIB_BLAS): $(C_SRC_BLAS) 
	$(CC) $(CFLAGS) -shared -fPIC $(C_SRC_BLAS) -lblas -o $(DYLIB_BLAS)

clean: 
	rm -fr $(JAVA_PACKAGES)/JaLAJniLite
	rm -f $(JNI_LAPACK_SRC)/c/include/jniLAPACK.h
	rm -f $(JAVA_HOME)/projects/JaLAJniLite_tests/*.class
	rm -f $(JAVA_HOME)/lib/liblapack_lite.dylib
	rm -f $(JAVA_HOME)/lib/libblas_lite.dylib
	rm -f $(JNI_BLAS_SRC)/c/include/jniCBLAS.h
	rm -f $(JAVA_HOME)/projects/JaLAJniLite_tests/*.txt
