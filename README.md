# ODKEncryption

Currently, sqlcipher is having trouble building. 
Right now the program works as an unencrypted database.
Just uncomment the lines with sqlite3_key to start using an encrypted database.
Remember that sqlite3_key only opens an already encrypted database, or encrypts a fresh one.

Things to install: 
sqlcipher
	which requires openssl and tcl*
	*tcl is required in making files and make test, but not in the actual usage of the program
	
installing openssl
	./configure > make > make test > make install

installing sqlcipher
	*** SQLITE_HAS_CODEC and SQLITE_TEMP_STORE must be defined when building ***
	./configure --enable-tempstore=yes CFLAGS="-DSQLITE_HAS_CODEC" \
	
	make
	make sqlite3.c  <-- this is the amalgamation file present in the android project
	make test 
