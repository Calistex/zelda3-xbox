XBE_TITLE = zelda3
GEN_XISO = $(XBE_TITLE).iso
NXDK_DIR = $(CURDIR)/../../../..
NXDK_SDL = y

SRCS:=$(wildcard ../../*.c ../../snes/*.c)

INCLUDES += \
			-I$(CURDIR)/../../  

EXTRA_OFLAGS = \
						-Ofast \
						-fsigned-char \
						-fpermissive

FLAGS	=	\
					-D__XBOX__ 


CFLAGS	+=	$(EXTRA_OFLAGS) $(INCLUDES) $(FLAGS)

CXXFLAGS +=	$(CFLAGS)

new_all: copy_resources all

include $(NXDK_DIR)/Makefile

copy_resources:
	@mkdir -p $(OUTPUT_DIR)
	@mkdir -p $(OUTPUT_DIR)/tables
	cp zelda3.ini $(OUTPUT_DIR)/zelda3.ini


clean_local:
	@echo clean ...
	rm -Rf ./bin
	find . -name '*.iso' -type f -delete