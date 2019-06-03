cmake_minimum_required(VERSION 3.0)
project(adflib VERSION 0.7.12)

option(EXAMPLES "Build examples" ON)
option(REGTESTS "Build regression tests" ON)
option(BUILD_SHARED_LIBS "Build shared library instead of static" OFF)

add_subdirectory(src)
add_subdirectory(doc)
if(EXAMPLES)
	add_subdirectory(examples)
endif()
if(REGTESTS)
	add_subdirectory(regtests/Test)
endif()

