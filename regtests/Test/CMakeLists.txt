cmake_minimum_required(VERSION 3.0)

#enable_testing()

add_executable(fl_test fl_test.c)
target_link_libraries(fl_test adf)

add_executable(fl_test2 fl_test2.c)
target_link_libraries(fl_test2 adf)

add_executable(dir_test dir_test.c)
target_link_libraries(dir_test adf)

add_executable(dir_test2 dir_test2.c)
target_link_libraries(dir_test2 adf)

add_executable(hd_test hd_test.c)
target_link_libraries(hd_test adf)

add_executable(hd_test2 hd_test2.c)
target_link_libraries(hd_test2 adf)

add_executable(hd_test3 hd_test3.c)
target_link_libraries(hd_test3 adf)

add_executable(file_test file_test.c)
target_link_libraries(file_test adf)

add_executable(file_test2 file_test2.c)
target_link_libraries(file_test2 adf)

add_executable(file_test3 file_test3.c)
target_link_libraries(file_test3 adf)

add_executable(del_test del_test.c)
target_link_libraries(del_test adf)

add_executable(bootdisk bootdisk.c)
target_link_libraries(bootdisk adf)

add_executable(rename rename.c)
target_link_libraries(rename adf)

add_executable(hardfile hardfile.c)
target_link_libraries(hardfile adf)

add_executable(rename2 rename2.c)
target_link_libraries(rename2 adf)

add_executable(hardfile2 hardfile2.c)
target_link_libraries(hardfile2 adf)

add_executable(access access.c)
target_link_libraries(access adf)

add_executable(comment comment.c)
target_link_libraries(comment adf)

add_executable(undel undel.c)
target_link_libraries(undel adf)

add_executable(readonly readonly.c)
target_link_libraries(readonly adf)

add_executable(undel2 undel2.c)
target_link_libraries(undel2 adf)

add_executable(dispsect dispsect.c)
target_link_libraries(dispsect adf)

add_executable(progbar progbar.c)
target_link_libraries(progbar adf)

add_executable(undel3 undel3.c)
target_link_libraries(undel3 adf)
