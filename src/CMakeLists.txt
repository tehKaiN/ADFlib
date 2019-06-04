cmake_minimum_required(VERSION 3.0)

file(WRITE "${CMAKE_CURRENT_BINARY_DIR}/config.h" "")

set(NATIVE_DIR generic)

set(libadf_SOURCES
	adf_hd.c
	adf_disk.c
	adf_raw.c
	adf_bitm.c
	adf_dump.c
	adf_util.c
	adf_env.c
	"${NATIVE_DIR}/adf_nativ.c"
	adf_dir.c
	adf_file.c
	adf_cache.c
	adf_link.c
	adf_salv.c)

set(libadf_HEADERS
	adf_defs.h
	adf_blk.h
	adf_err.h
	adf_str.h
	adflib.h
	adf_bitm.h
	adf_cache.h
	adf_dir.h
	adf_disk.h
	adf_dump.h
	adf_env.h
	adf_file.h
	adf_hd.h
	adf_link.h
	adf_raw.h
	adf_salv.h
	adf_util.h
	defendian.h
	hd_blk.h
	prefix.h
	"${NATIVE_DIR}/adf_nativ.h")

add_library(adf ${libadf_SOURCES} ${libadf_HEADERS})

set_target_properties(adf PROPERTIES VERSION 0.0.12 SOVERSION 0)

target_include_directories(adf
	PUBLIC
		$<INSTALL_INTERFACE:include/adflib>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/${NATIVE_DIR}>
	PRIVATE
		${CMAKE_CURRENT_BINARY_DIR}
)

target_compile_definitions(adf PRIVATE
	_XOPEN_SOURCE=500	# Need this for strdup with current glibc
	$<$<AND:${WIN32},$<BOOL:${BUILD_SHARED_LIBS}>>: WIN32DLL>
)

target_compile_options(adf PRIVATE
	# clang/GCC flags
	$<$<OR:$<CXX_COMPILER_ID:Clang>,$<CXX_COMPILER_ID:GNU>>: -std=c99 -pedantic -Wall >
)

install(TARGETS adf
	LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR})
install(FILES ${libadf_HEADERS} DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}/adflib")
