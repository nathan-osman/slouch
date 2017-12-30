configure_file(config.h.in "${CMAKE_CURRENT_BINARY_DIR}/config.h")

set(SRC
    main.cpp
)

add_executable(slouch WIN32 ${SRC})

set_target_properties(slouch PROPERTIES
    CXX_STANDARD 11
)

target_include_directories(slouch PUBLIC
    "${CMAKE_CURRENT_BINARY_DIR}"
)

target_link_libraries(slouch Qt5::Network Qt5::Widgets)

install(TARGETS slouch
    DESTINATION bin
)
