cmake_minimum_required(VERSION 3.5)

project(xhidecursor LANGUAGES C)

find_package(X11 REQUIRED)
find_library(XFIXES_LIB Xfixes REQUIRED)
find_library(XI_LIB Xi REQUIRED)

add_executable(${PROJECT_NAME}
    main.c
)

target_link_libraries(${PROJECT_NAME}
    X11::X11
    ${XFIXES_LIB}
    ${XI_LIB}
)

install(TARGETS ${PROJECT_NAME}
    RUNTIME DESTINATION bin
)

