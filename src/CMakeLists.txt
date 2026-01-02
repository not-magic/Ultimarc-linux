cmake_minimum_required(VERSION 3.10)
project(Ultimarc-linux VERSION 1.2 LANGUAGES C)

# Find required packages
find_package(PkgConfig REQUIRED)
pkg_check_modules(JSON REQUIRED json-c>=0.11)
pkg_check_modules(LIBUSB REQUIRED libusb-1.0>=1.0.18)

# Library sources
set(ULTIMARC_LIB_SOURCES
    libs/ultimarc.c
    libs/ipac.c
    libs/ultrastik.c
    libs/pacLED.c
    libs/common.c
    libs/pacdrive.c
    libs/ipacultimate.c
    libs/ipacseries.c
    libs/ulboard.c
    libs/usbbutton.c
    libs/servostik.c
    libs/uhid.c
)

# Create the ultimarc library
add_library(ultimarc STATIC ${ULTIMARC_LIB_SOURCES})

target_include_directories(ultimarc
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PUBLIC ${JSON_INCLUDE_DIRS}
    PUBLIC ${LIBUSB_INCLUDE_DIRS}
)

target_link_libraries(ultimarc
    PUBLIC ${JSON_LIBRARIES}
    PUBLIC ${LIBUSB_LIBRARIES}
)

# Create the umtool executable
add_executable(umtool umtool/main.c)

target_include_directories(umtool
    PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(umtool
    PRIVATE ultimarc
)

# Installation rules
install(TARGETS umtool DESTINATION bin)
install(TARGETS ultimarc DESTINATION lib)
install(FILES libs/ultimarc.h libs/ulboard.h DESTINATION include/ultimarc)
