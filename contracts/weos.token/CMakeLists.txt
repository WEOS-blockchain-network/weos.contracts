add_contract(weos.token weos.token ${CMAKE_CURRENT_SOURCE_DIR}/src/weos.token.cpp)

target_include_directories(weos.token
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(weos.token
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/weos.token.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/weos.token.contracts.md @ONLY )

target_compile_options( weos.token PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
