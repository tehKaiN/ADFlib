cmake_minimum_required(VERSION 3.0)

include(GNUInstallDirs)

set(doc_DATA
	${CMAKE_SOURCE_DIR}/README
	${CMAKE_SOURCE_DIR}/AUTHORS
	${CMAKE_SOURCE_DIR}/COPYING
	${CMAKE_SOURCE_DIR}/ChangeLog
	${CMAKE_SOURCE_DIR}/NEWS)

set(nobase_doc_DATA
	FAQ/image/adf_file.gif
	FAQ/adf_info.html
	FAQ/adf_info.txt
	FAQ/adf_info_V0_9.txt
	api_device.html
	api_dir.html
	api_env.html
	api_file.html
	api_index.html
	api_native.html
	api_salv.html
	api_volume.html
	API.txt
	version0.7.9d_gary.txt)

install(FILES ${doc_DATA} ${nobase_doc_DATA} DESTINATION ${CMAKE_INSTALL_DOCDIR})
