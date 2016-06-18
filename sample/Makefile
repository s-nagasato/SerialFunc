# This Makefile is create next execute binary files.
#    1.self_com
#           


CFLAGS      = -Wall -O2 -lm 
#TARGET      = arm-none-linux-gnueabi-
#TARGET      = arm-linux-gnueabi-
#TARGET	=
CC          = $(TARGET)gcc
STRIP       = $(TARGET)strip
INSTALL_DIR = /usr/local/bin
USERLIBS    = -lSerialFunc
PROGS       = self_com port2_com\


##### Make all######################
all : $(PROGS)


### Program build ###########################################################
self_com : self_com.c $(USERLIBS)
	$(CC) $(CFLAGS) -o self_com self_com.c \
		$(USERLIBS) -lm 
	$(STRIP) self_com

port2_com : port2_com.c $(USERLIBS)
	$(CC) $(CFLAGS) -o port2_com port2_com.c \
		$(USERLIBS) -lm -lSerialFunc
	$(STRIP) port2_com

##### Make install #################
install :
	cp -a $(PROGS) $(INSTALL_DIR)
	chown root.root $(INSTALL_DIR)/$(PROGS)
	chown 4755 $(INSTALL_DIR)/$(PROGS)


##### Make uninstall ###############
uninstall :
	rm -f $(INSTALL_DIR)/$(PROGS)


##### Make clean ###################
clean:
	rm -f $(PROGS)

