CXX = g++
CXXFLAGS = -Wall -std=c++11 -g -I.

DIR_OUT = out/
DIR_SRC = src/
DIR_INC = inc/
# find all file .cpp in DIR_SRC
SRCS = $(wildcard $(DIR_SRC)/*.cpp)
# find all file .cpp in DIR_INC
INCS = $(wildcard $(DIR_INC)/*.hpp)
TARGET = main

# create OBJS as a list of file .o
OBJS = $(patsubst $(DIR_SRC)/%.cpp, $(DIR_OUT)/%.o, $(SRCS))

# Compile .cpp to .o
$(DIR_OUT)/%.o: src/%.cpp $(INCS)
	@mkdir -p $(DIR_OUT)
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Make target
all: $(OBJS)
	$(CXX) $(CXXFLAGS) -o $(TARGET) $(OBJS)

# Clean target
clean:
	rm -rf $(DIR_OUT) $(TARGET) main.dSYM

# make for 'all' and 'clean' are not real files. Mark them as lable for command
.PHONY: all clean
