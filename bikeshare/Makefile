DIRNAME := $(notdir $(CURDIR))
LOGOS := $(filter-out $(wildcard *-qrcode.svg), $(wildcard *.svg))
QRCODES := $(addsuffix -qrcode.svg, $(basename $(LOGOS)))
ifeq ($(SHOWENV),)
else
 export
endif
all: $(QRCODES)
%-qrcode.svg: %.svg %.link $(wildcard ../*.py)
	$(MAKE) -C .. $(DIRNAME)/$@
env:
ifeq ($(SHOWENV),)
	$(MAKE) SHOWENV=1 $@
else
	$@
endif
