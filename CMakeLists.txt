# set minimum cmake version
cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

# project name and language
project(FTP LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(ftp_client_dir ${CMAKE_CURRENT_SOURCE_DIR}/FTPClient)
set(ftp_server_dir ${CMAKE_CURRENT_SOURCE_DIR}/FTPServer)

file(GLOB client_sources "${ftp_client_dir}/*.cpp")
file(GLOB server_sources "${ftp_server_dir}/*.cpp")

add_executable(FTPClient ${client_sources})
add_executable(FTPServer ${server_sources})

target_link_directories(FTPClient PUBLIC ${ftp_client_dir})
target_link_directories(FTPServer PUBLIC ${ftp_server_dir})