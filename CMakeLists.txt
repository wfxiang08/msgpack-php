cmake_minimum_required(VERSION 3.2)
project(msgpack_php)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# 使用php7.1，保持和线上代码一致
INCLUDE_DIRECTORIES(
    /usr/local/Cellar/php71/7.1.5_17/include/php
    /usr/local/Cellar/php71/7.1.5_17/include/php/main
    /usr/local/Cellar/php71/7.1.5_17/include/php/Zend
    ./
)

set(SOURCE_FILES
    msgpack/pack_define.h
    msgpack/pack_template.h
    msgpack/sysdep.h
    msgpack/unpack_define.h
    msgpack/unpack_template.h
    msgpack/version.h
    msgpack.c
    msgpack_class.c
    msgpack_class.h
    msgpack_convert.c
    msgpack_convert.h
    msgpack_errors.h
    msgpack_pack.c
    msgpack_pack.h
    msgpack_unpack.c
    msgpack_unpack.h
    php_msgpack.h)

add_executable(msgpack_php ${SOURCE_FILES})