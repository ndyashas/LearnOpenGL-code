CXX := g++
CXXFLAGS := -Wall -lglfw3 -ldl -lXrandr -lXi -lX11 -lGL -lpthread -lm
INCLUDE := -I ../common/include -I ./include

CXXSRC := $(wildcard ./src/*.cpp)
CXXSRC += $(wildcard ../common/src/*.cpp)
CSRC := $(wildcard ./src/*.c)
CSRC += $(wildcard ../common/src/*.c)

CXXOBJECTS := $(CXXSRC:.cpp=.cpp.o)
COBJECTS := $(CSRC:.c=.c.o)

OBJECTS := $(CXXOBJECTS) $(COBJECTS)


debug-bin: $(OBJECTS)
	$(CXX) $(INCLUDE) $^ $(CXXFLAGS) -o $@

%.cpp.o: %.cpp
	$(CXX) $(INCLUDE) -c $^ $(CXXFLAGS) -o $@

%.c.o: %.c
	$(CXX) $(INCLUDE) -c $^ $(CXXFLAGS) -o $@

clean:
	$(RM) $(OBJECTS) debug-bin *~
