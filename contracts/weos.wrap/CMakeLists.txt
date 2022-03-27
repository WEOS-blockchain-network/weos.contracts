add_contract(weos.wrap weos.wrap ${CMAKE_CURRENT_SOURCE_DIR}/src/weos.wrap.cpp)

target_include_directories(weos.wrap
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(weos.wrap
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/weos.wrap.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/weos.wrap.contracts.md @ONLY )

target_compile_options( weos.wrap PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
