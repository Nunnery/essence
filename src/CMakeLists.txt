# get a list of all .h files
file(GLOB HDRS "*.h" "*/*.h" "*/**/*.h")

# get a list of all .c files
file(GLOB C_SRCS "*.c" "*/*.c" "*/**/*.c")

# get a list of all .cpp files
file(GLOB CPP_SRCS "*.cpp" "*/*.cpp" "*/**/*.cpp")

add_executable(essence ${HDRS} ${C_SRCS} ${CPP_SRCS})