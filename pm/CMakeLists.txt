# Configure dependencies here
CPMUsePackageLock(package-lock.cmake)

# {fmt}
set(FMT_TEST OFF CACHE BOOL "")
CPMGetPackage(fmt)

target_link_libraries(${PROJECT_NAME}
    PRIVATE
        fmt
)
