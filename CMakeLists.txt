cmake_minimum_required(VERSION 3.8)

PROJECT(dmrapidjson)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()
ModuleSetWinCompilerFlags()

InterfaceImport("dmrapidjson" "include" "")
ExeImport("example" "dmrapidjson")
ExeImport("test" "dmrapidjson")

#ADD_CUSTOM_COMMAND(
#TARGET dmrapidjsontest
#PRE_BUILD
#COMMAND ${CMAKE_COMMAND} -E copy_if_different
#${CMAKE_CURRENT_SOURCE_DIR}/config/test.csv
#$<TARGET_FILE_DIR:dmrapidjsontest>
#)

#INSTALL(DIRECTORY include/ DESTINATION include)
#INSTALL(TARGETS dmrapidjson
#        RUNTIME DESTINATION bin
#        LIBRARY DESTINATION lib
#        ARCHIVE DESTINATION lib)

#SET(DMRAPIDJSON_LIBS "dmrapidjson")
#MARK_AS_ADVANCED(${DMRAPIDJSON_LIBS})