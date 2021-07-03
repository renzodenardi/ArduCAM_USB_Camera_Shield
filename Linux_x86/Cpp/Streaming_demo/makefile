CC			= g++

LIBS		= -lArduCamLib -lusb-1.0  -lpthread -larducam_config_parser `pkg-config --cflags --libs opencv`
FLAGS		= -L. -I. -std=gnu++11 -g
LDIR		= ./Arducam_SDK

ArduCam_Demo:ArduCam_Demo.cpp $(LDIR)/ArduCamLib.h
	$(CC) $^ -o $@ $(LIBS) $(FLAGS) 

ArduCam_Demo_test:ArduCam_Demo_test.cpp  $(LDIR)/ArduCamLib.h
	$(CC) $^ -o $@ $(LIBS) $(FLAGS) 
	
.PHONY:clean

clean:
	rm -f ArduCam_Demo

.PHONY:install-sdk

install-sdk:
	cp -d $(LDIR)/lib*.so* /usr/lib
	cp -d $(LDIR)/ArduCamLib.h /usr/include/
        
.PHONY:uninstall-sdk

uninstall-sdk:
	rm /usr/lib/libArduCam*
	rm /usr/include/ArduCamLib.h
