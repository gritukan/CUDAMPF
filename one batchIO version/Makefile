#################################################################
# Makefile for building CUDA project with multiple .cu sources
# Output executable: mpf
#################################################################

# Compiler
NVCC       := nvcc

# Include paths
INCLUDES   := -Icuda_common

# Linker flags
LIBS       := -lcuda -ldl -lnvrtc

# Source files
SRC_CU     := degenerate.cu \
              main_function.cu \
              model_config.cu \
              other_function.cu \
              read_file.cu \
              RTC_MSV.cu \
              RTC_SSV.cu \
              RTC_VIT.cu

# Object files (replace .cu with .o)
OBJ        := $(SRC_CU:.cu=.o)

# Target executable
TARGET     := mpf

# Phony targets
.PHONY: all clean

# Default target
all: $(TARGET)

# Link step
$(TARGET): $(OBJ)
	$(NVCC) -o $@ $(OBJ) $(LIBS)

# Compile each .cu to .o
%.o: %.cu
	$(NVCC) $(INCLUDES) -c $< -o $@

# Clean up
clean:
	rm -f $(OBJ) $(TARGET)

