CXX := g++
CXXFLAGS := -Wall -lglfw3 -ldl -lXrandr -lXi -lX11 -lGL -lpthread -lm
INCLUDE := -I ../common/include -I ./include

CXXSRC := $(wildcard ./src/*.cc)
CXXSRC += $(wildcard ../common/src/*.cc)
CSRC := $(wildcard ./src/*.c)
CSRC += $(wildcard ../common/src/*.c)

CXXOBJECTS := $(CXXSRC:.cc=.cc.o)
COBJECTS := $(CSRC:.c=.c.o)

OBJECTS := $(CXXOBJECTS) $(COBJECTS)

debug-bin: $(OBJECTS)
	$(CXX) $(INCLUDE) $^ $(CXXFLAGS) -o $@

%.cc.o: %.cc
	$(CXX) $(INCLUDE) -c $^ $(CXXFLAGS) -o $@

%.c.o: %.c
	$(CXX) $(INCLUDE) -c $^ $(CXXFLAGS) -o $@

clean:
	$(RM) $(OBJECTS) debug-bin *~

.PHONY: clean
