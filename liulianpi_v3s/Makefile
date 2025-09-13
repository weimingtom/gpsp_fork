# gpSP makefile
# Gilead Kutnick - Exophase
# pandora port - notaz
# raspberry pi - DPR

# Global definitions

#CC        = gcc
CC      = /home/wmt/work_v3s/gcc-linaro-6.3.1-2017.05-x86_64_arm-linux-gnueabihf/bin/arm-linux-gnueabihf-gcc

OBJS      = rpi.o main.o cpu.o memory.o video.o input.o sound.o gui.o \
            cheats.o zip.o  arm_stub.o  warm.o cpu_threaded.o \
	     video_blend.o 

BIN       = gpsp

# Platform specific definitions 

VPATH      += .. ../arm
CFLAGS     += -DARM_ARCH -DRPI_BUILD -Wall
CFLAGS	   += -marm -mcpu=cortex-a7  -I./include -O0 -g3

#-mfpu=neon-vfpv4 -mfloat-abi=hard

#-marm -mcpu=cortex-a7 -mfpu=neon-vfpv4 -mfloat-abi=hard 
#-fgnu89-inline -Ofast -mtune=cortex-a7  
#-march=armv7-a 
LIBS       += -ldl -lpthread -lz -L./lib
#LIBS       += -L/usr/lib/ -lopenmaxil  -lvcos -lvchiq_arm  -lrt 

# Dependencies
#ifeq ($(origin SDL_CFLAGS) $(origin SDL_LDLIBS), undefined undefined)
#  SDL_CONFIG ?= sdl-config
#  ifeq ($(shell which $(SDL_CONFIG) 2>/dev/null),)
#    $(error No SDL development libraries found!)
#  endif
#  SDL_CFLAGS += $(shell $(SDL_CONFIG) --cflags)
#  SDL_LIBS += $(shell $(SDL_CONFIG) --libs)
#endif
#CFLAGS += $(SDL_CFLAGS)
#LIBS += $(SDL_LIBS)
CFLAGS += -I./include/SDL
LIBS += -lSDL

# Compilation:

all: $(BIN)

%.o: %.S
	$(CC) $(CFLAGS) -c -o $@ $<


cpu.o cpu_threaded.o: CFLAGS += -Wno-unused-variable -Wno-unused-label

$(BIN): $(OBJS)
	$(CC) $(OBJS) $(LIBS) -o $(BIN)

clean:
	rm -f *.o $(BIN)

debug:
	gdb-multiarch gpsp core
