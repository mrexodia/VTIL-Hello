project(VTIL-Hello)

# Simple executable
add_executable(${PROJECT_NAME} VTIL-Hello.cpp)

# Link to VTIL
target_link_libraries(${PROJECT_NAME} PRIVATE VTIL)