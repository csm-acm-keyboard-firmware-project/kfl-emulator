cmake_minimum_required(VERSION 3.0)
project(KFL-emulator)

# Find SFML package
find_package(SFML 2.5 COMPONENTS graphics audio REQUIRED)

# Set c++ standard
set(CMAKE_CXX_STANDARD 11)

# Path to source files
set(SOURCE_DIR src)

# Add source files
file(GLOB_RECURSE SOURCES ${SOURCE_DIR}/*.cpp)
file(GLOB_RECURSE HEADERS ${SOURCE_DIR}/*.h)

# Create executable
add_executable(KFL-emulator ${SOURCES} ${HEADERS})

# Include header files
target_include_directories(KFL-emulator PRIVATE ${SOURCE_DIR})

# Link SFML libraries to project
target_link_libraries(KFL-emulator sfml-graphics sfml-audio)
