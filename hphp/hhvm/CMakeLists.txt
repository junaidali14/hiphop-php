set(CXX_SOURCES)
auto_sources(files "*.cpp" "")
list(APPEND CXX_SOURCES ${files})

add_executable(hhvm ${CXX_SOURCES})
target_link_libraries(hhvm hphp_analysis hphp_runtime_static ext_hhvm_static)

install(TARGETS hhvm DESTINATION bin)
install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/../../bin/systemlib.php DESTINATION bin)

