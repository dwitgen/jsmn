idf_component_register(
    SRCS "jsmn.h"
//    INCLUDE_DIRS "include"
)

set_target_properties(${COMPONENT_LIB} PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/.pioenvs/homeassist03"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/.pioenvs/homeassist03"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/.pioenvs/homeassist03"
)

if(CONFIG_JSMN_PARENT_LINKS)
    target_compile_definitions(${COMPONENT_LIB} INTERFACE "-DJSMN_PARENT_LINKS")
endif()

if(CONFIG_JSMN_STRICT)
    target_compile_definitions(${COMPONENT_LIB} INTERFACE "-DJSMN_STRICT")
endif()

if(CONFIG_JSMN_STATIC)
    target_compile_definitions(${COMPONENT_LIB} INTERFACE "-DJSMN_STATIC")
endif()

