CXX = g++
CXX_STANDARD = c++17
CXXFLAGS = -Wall -Wextra -Wpedantic -std=$(CXX_STANDARD) -g -I $(DIR_INC)

DIR_BUILD = build
DIR_SRC = src
DIR_INC = inc
# all file .cpp in DIR_SRC
SRCS = $(wildcard $(DIR_SRC)/*.cpp)
TARGET = main

# create OBJECTS as a list of file .o
OBJECTS = $(patsubst $(DIR_SRC)/%.cpp, $(DIR_BUILD)/%.o, $(SRCS))

# Compile .cpp to .o
$(DIR_BUILD)/%.o: $(DIR_SRC)/%.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Make target
all: prepare build
	@echo "build successful"

# create folder build if it's not exist
prepare:
	@mkdir -p $(DIR_BUILD)

# build source code
build: $(OBJECTS)
	$(CXX) $(CXXFLAGS) -o $(DIR_BUILD)/$(TARGET) $(OBJECTS)

# Clean build
clean:
	rm -rf $(DIR_BUILD)

# Make for target is lable for command, not real files
.PHONY: all clean
