file(GLOB_RECURSE server_SRCS *.cpp *.h)

set(server_SRCS
    ${server_SRCS}
    ${TEMPLATES_SRC}
        log/Logger.h log/Logger.cpp)

# Create the application
add_library(server SHARED ${server_SRCS})

# Link to Cutelyst
target_link_libraries(server
    Cutelyst::Core
    Cutelyst::StaticSimple
    Qt5::Core
    Qt5::Network
)

