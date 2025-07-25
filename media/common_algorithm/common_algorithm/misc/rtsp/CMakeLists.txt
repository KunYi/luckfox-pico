
cmake_minimum_required(VERSION 3.10)

project(librtsp C)

set(SOURCES
    rtsp_demo.c
    rtsp_msg.c
    rtp_enc.c
    stream_queue.c
    utils.c
)

set(PUBLIC_HEADERS
    rtsp_demo.h
    rtsp_msg.h
    rtp_enc.h
    stream_queue.h
    utils.h
    comm.h
    queue.h
)

add_compile_options(-g -Wall)
add_compile_definitions(__LINUX__)

add_library(rtsp STATIC ${SOURCES})

install(TARGETS rtsp
    ARCHIVE DESTINATION lib
)

install(FILES rtsp_demo.h
    DESTINATION include
)
