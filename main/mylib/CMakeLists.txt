cmake_minimum_required(VERSION 3.12)

set(SOURCE_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/src)
set(INCLUDE_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/include)

#Include the whole include directory for this directory
include_directories(${INCLUDE_FOLDER})

#Source files
set(SOURCESCLIENT ${SOURCE_FOLDER}/ThunderChatClient.cpp)
set(SOURCESSERVER ${SOURCE_FOLDER}/ThunderChatServer.cpp)

#Headers files (for IntelliSense)
set(HEADERSCLIENT ${INCLUDE_FOLDER}/ThunderChatClient.hpp)
set(HEADERSSERVER ${INCLUDE_FOLDER}/ThunderChatServer.hpp)

#Main lib
add_library(client_lib ${SOURCESCLIENT} ${HEADERSCLIENT})
add_library(server_lib ${SOURCESSERVER} ${HEADERSSERVER})
target_include_directories(client_lib SYSTEM INTERFACE ${INCLUDE_FOLDER})
target_include_directories(server_lib SYSTEM INTERFACE ${INCLUDE_FOLDER})
