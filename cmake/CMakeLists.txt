set(CONF_BUILD_DEPEND_PATH "${CMAKE_CURRENT_SOURCE_DIR}/build_deps")

# CPM Configuration
set(CONF_BUILD_CPM_PATH "${CONF_BUILD_DEPEND_PATH}/CPM.cmake")

if(NOT (EXISTS ${CONF_BUILD_CPM_PATH}))
    set(CPM_DOWNLOAD_VERSION 0.34.3) 
    message(STATUS "Downloading CPM.cmake @ ${CPM_DOWNLOAD_VERSION} to ${CONF_BUILD_CPM_PATH}")
    file(DOWNLOAD
        https://github.com/cpm-cmake/CPM.cmake/releases/download/v${CPM_DOWNLOAD_VERSION}/CPM.cmake
        ${CONF_BUILD_CPM_PATH}
    )
endif()

include(${CONF_BUILD_CPM_PATH})
