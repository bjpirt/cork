# this is quick and dirty, really not best practice

include_directories(math/)
include_directories(mesh/)
include_directories(rawmesh/)
include_directories(accel/)
include_directories(file_formats/)
include_directories(util/)
include_directories(isct/)

set (CORK_SOURCE_FILES file_formats/files.cpp file_formats/ifs.cpp file_formats/off.cpp file_formats/stl.cpp isct/empty3d.cpp isct/quantization.cpp isct/triangle.c util/log.cpp util/timer.cpp cork.cpp) 
add_library(cork SHARED ${CORK_SOURCE_FILES})
target_link_libraries(cork ${GMP_LIBRARIES})

install(TARGETS cork DESTINATION lib)
install(FILES cork.h DESTINATION include)

add_executable(cork_tool main.cpp)
target_link_libraries(cork_tool cork)
