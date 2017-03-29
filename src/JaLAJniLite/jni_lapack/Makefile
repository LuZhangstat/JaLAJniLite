DEST = .
CC = gcc
CFLAGS = $(INCLUDE) $(LIB) 

JAVA_HOME = ../../..
JAVA_PACKAGES = $(JAVA_HOME)/packages
JAVA_LIB = $(JAVA_HOME)/lib

JNI_SRC = $(JAVA_HOME)/src/jama_lite/jni_lapack

INCLUDE = -I$(JNI_SRC)/c/include \
	-I$(JAVA_HOME)/include 
LIB = -L/usr/local/lib -L$(JAVA_LIB)
C_SRC = $(JNI_SRC)/c/jniLAPACK.c 
DYLIB = $(JAVA_HOME)/lib/liblapack_lite.so

# For package Jama
JC = javac
JH = javah
JFLAGS = -d
JAVA_SRC = $(JNI_SRC)/java/jniLAPACK.java
PACKAGE = $(JAVA_PACKAGES)/jama_lite
HEADER = $(JNI_SRC)/c/include/jniLAPACK.h

# header file jniLAPACKE.h


all: $(PACKAGE) $(HEADER) $(DYLIB)

$(PACKAGE): $(JAVA_SRC)
	$(JC) $(JFLAGS) $(JAVA_PACKAGES) $(JAVA_SRC)

$(HEADER): 
	$(JH) -o $(HEADER) -classpath $(JAVA_PACKAGES) jama_lite.jni_lapack.jniLAPACK

$(DYLIB):  $(C_SRC)
	$(CC) $(CFLAGS) -shared -fPIC $(C_SRC) -llapack -o $(DYLIB)

clean: 
	rm -f $(JAVA_HOME)/lib/liblapack_lite.so
	rm -fr $(JAVA_PACKAGES)/jama_jni
	rm -f $(JNI_SRC)/c/include/jniLAPACK.h
	rm -f $(JAVA_HOME)/projects/jama_lite_tests/*.class
	rm -f $(JAVA_HOME)/projects/jama_lite_tests/*.txt
