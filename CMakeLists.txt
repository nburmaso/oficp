cmake_minimum_required(VERSION 2.8)
project(oficp C)

set(C_STANDARD 99)

include_directories(${PROJECT_SOURCE_DIR}/include
                    /hpcscratch/user/nburmaso/libfabric/install/include
                    /hpcscratch/user/nburmaso/libfabric/include
                    /hpcscratch/user/nburmaso/libfabric)

file(GLOB headers ${PROJECT_SOURCE_DIR}/include/*.h)
file(GLOB sources ${PROJECT_SOURCE_DIR}/src/*.c)

add_executable(oficp main.c ${sources} ${headers})

# set_property(TARGET oficp PROPERTY C_STANDARD 99)

target_link_libraries(oficp
                      /hpcscratch/user/nburmaso/libfabric/install/lib/libfabric.so)
