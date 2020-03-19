# Set CMake minimum version and CMake policy required by UrhoCommon module
cmake_minimum_required (VERSION 3.10.2)
if (COMMAND cmake_policy)
    # Libraries linked via full path no longer produce linker search paths
    cmake_policy (SET CMP0003 NEW)
    # INTERFACE_LINK_LIBRARIES defines the link interface
    cmake_policy (SET CMP0022 NEW)
    # Disallow use of the LOCATION target property - so we set to OLD as we still need it
    cmake_policy (SET CMP0026 OLD)
    # MACOSX_RPATH is enabled by default
    cmake_policy (SET CMP0042 NEW)
    # Honor the visibility properties for SHARED target types only
    cmake_policy (SET CMP0063 OLD)
endif ()

# Project name
project (Urho3DCMakeTest)

# Set CMake modules search path
set (CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/CMake/Modules)

# Include UrhoCommon.cmake module after setting project name
include (UrhoCommon)

# Define target name
set (TARGET_NAME Urho3DCMakeTest)

# Define source code files
define_source_files (GLOB_CPP_PATTERNS ${CMAKE_SOURCE_DIR}/Source/* GLOB_H_PATTERNS ${CMAKE_SOURCE_DIR}/Source/*)

# Group souce code file with physical their folders
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SOURCE_FILES})

# Define resource directories of Urho3D
define_resource_dirs ()

# Setup main executable
setup_main_executable ()