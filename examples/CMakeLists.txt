cmake_minimum_required(VERSION 3.0)
project(unadf VERSION 1.0)

add_executable(unadf unadf.c)
target_link_libraries(unadf adf)
set_target_properties(unadf PROPERTIES INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/${CMAKE_INSTALL_LIBDIR}")
install(TARGETS unadf
	RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
