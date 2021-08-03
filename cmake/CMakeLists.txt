set(PROJECT_BUILD_DEP_PATH "${CMAKE_CURRENT_SOURCE_DIR}/build_deps")

if(NOT (EXISTS ${PROJECT_BUILD_DEP_PATH}/CPM.cmake))
    set(CPM_RELEASE_VERISON_TAG 0.32.2)
    
    message(STATUS "Downloading CPM.cmake")
    file(DOWNLOAD https://github.com/TheLartians/CPM.cmake/releases/download/v${CPM_RELEASE_VERISON_TAG}/CPM.cmake ${PROJECT_BUILD_DEP_PATH}/CPM.cmake)
endif()

list(APPEND CMAKE_MODULE_PATH ${PROJECT_BUILD_DEP_PATH})
include(CPM)
