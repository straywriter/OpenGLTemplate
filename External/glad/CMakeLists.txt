project(glad)

set(GLAD_BUILD_SHARED OFF CACHE BOOL "build glad to shared")

if(GLAD_BUILD_SHARED)
    add_library(glad SHARED
        "include/glad/glad.h" 
        "include/KHR/khrplatform.h" 
        "src/glad.c")
    target_compile_definitions(glad 
    PUBLIC GLAD_GLAPI_EXPORT 
    PRIVATE GLAD_GLAPI_EXPORT_BUILD)
else()
    add_library(glad STATIC
        "include/glad/glad.h" 
        "include/KHR/khrplatform.h" 
        "src/glad.c")
endif()
target_include_directories(glad PUBLIC "include")