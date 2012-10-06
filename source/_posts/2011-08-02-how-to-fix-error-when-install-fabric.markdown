---
layout: post
title: "How to Fix Error when Install Fabric"
date: 2011-08-02 23:04
comments: true
categories: [python, tips, fabric]

---

    Installing collected packages: pycrypto, paramiko
    Running setup.py install for pycrypto
	warning: GMP library not found; Not building Crypto.PublicKey._fastmath.
	building 'Crypto.Hash.MD2' extension
	gcc-4.2 -fno-strict-aliasing -fno-common -dynamic -fwrapv -Wall -Wstrict-prototypes -DENABLE_DTRACE -arch i386 -arch ppc -arch x86_64 -pipe -std=c99 -O3 -fomit-frame-pointer -Isrc/ -I/System/Library/Frameworks/Python.framework/Versions/2.6/include/python2.6 -c src/MD2.c -o build/temp.macosx-10.6-universal-2.6/src/MD2.o
	/usr/libexec/gcc/powerpc-apple-darwin10/4.2.1/as: assembler (/usr/bin/../local/libexec/as/ppc/as or /usr/bin/../local/libexec/gcc/darwin/ppc/as) for architecture ppc not installed
	Installed assemblers are:
	/usr/bin/../libexec/as/x86_64/as for architecture x86_64
	/usr/bin/../libexec/as/i386/as for architecture i386
	/usr/bin/../libexec/as/arm/as for architecture arm
	src/MD2.c:134: fatal error: error writing to -: Broken pipe
	compilation terminated.
	lipo: can't open input file: /var/tmp//cc2qfvbZ.out (No such file or directory)
	error: command 'gcc-4.2' failed with exit status 1
	Complete output from command /usr/bin/python -c "import setuptools;__file__='/Users/Kelvin/build/pycrypto/setup.py';execfile(__file__)" install --single-version-externally-managed --record /tmp/pip-4O2Z1I-record/install-record.txt:
	running install
	.....

	lipo: can't open input file: /var/tmp//cc1IbrXz.out (No such file or directory)

	error: command 'gcc-4.2' failed with exit status 1

WHEN YOU GOT ABOVE ERROR WHEN YOU INSTALL THE FABRIC, REFER TO THE FOLLOWING COMMAND:
```
sudo ARCHFLAGS="-arch i386 -arch x86_64" pip install Fabric
```

**Reason**: in Xcode 4, gcc removed the -arch ppc
