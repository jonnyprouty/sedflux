include_directories(${CMAKE_SOURCE_DIR}/ew)


########### next target ###############

SET(bing_SRCS bing_main.c)

add_executable(run_bing ${bing_SRCS})

target_link_libraries(run_bing bing-static sedflux-static)

install(
  PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/run_bing
  DESTINATION bin
  RENAME bing
  COMPONENT sedflux
)

########### next target ###############

set (bing_LIB_SRCS bing.c)

set_source_files_properties (${bing_LIB_SRCS} get_config_text.c PROPERTIES LANGUAGE C)
add_library(bing ${bing_LIB_SRCS} get_config_text.c)
add_library(bing-static STATIC ${bing_LIB_SRCS})

target_link_libraries(bing sedflux)

install(TARGETS bing DESTINATION lib COMPONENT sedflux)


########### install files ###############

install(FILES bing.h DESTINATION include/ew-2.0 COMPONENT sedflux)
