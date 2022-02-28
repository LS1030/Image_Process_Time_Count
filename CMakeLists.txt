cmake_minimum_required(VERSION 3.20)
project(Image_Process_Time_Count)

set(CMAKE_CXX_STANDARD 14)

#OpenCV
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# include
include_directories(${PROJECT_SOURCE_DIR}/Inc)

# SRC
aux_source_directory(${PROJECT_SOURCE_DIR}/Src USER_SRC)

# Set the output folder where your program will be created
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)

# link_libraries
set(LINK_LIB
        ${OpenCV_LIBS}
        )

add_executable(Image_Process_Time_Count ${USER_SRC})
target_link_libraries(Image_Process_Time_Count ${LINK_LIB})
