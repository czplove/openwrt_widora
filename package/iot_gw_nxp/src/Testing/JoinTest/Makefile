# ------------------------------------------------------------------
# Secure Joiner Test makefile
# ------------------------------------------------------------------
# Author:    nlv10677
# Copyright: NXP B.V. 2014. All rights reserved
# ------------------------------------------------------------------

TARGET = iot_jt
OTHERS = linkinfo.json secjoin.json joinsecure.json

INCLUDES = -I../../IotCommon
OBJECTS = jt_main.o \
	../../IotCommon/atoi.o \
	../../IotCommon/iotError.o \
	../../IotCommon/json.o \
	../../IotCommon/fileCreate.o \
	../../IotCommon/queue.o \
	../../IotCommon/socket.o \
	../../IotCommon/dump.o \
	../../IotCommon/iotSemaphore.o \
	../../IotCommon/newLog.o


%.o: %.c $(HEADERS)
	$(CC) $(CFLAGS) $(INCLUDES) -Wall -g -c $< -o $@

all: clean build

build: $(OBJECTS)
	$(CC) $(OBJECTS) -o $(TARGET) -lc
	mkdir -p ../../swupdate/images/usr/bin/
	mkdir -p ../../swupdate/images/usr/share/iot/
	cp -f $(TARGET) ../../swupdate/images/usr/bin/
	cp -f $(OTHERS) ../../swupdate/images/usr/share/iot/
clean:
	-rm -f $(OBJECTS)
	-rm -f $(TARGET)

