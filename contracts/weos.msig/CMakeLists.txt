add_contract(weos.msig weos.msig ${CMAKE_CURRENT_SOURCE_DIR}/src/weos.msig.cpp)

target_include_directories(weos.msig
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(weos.msig
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/weos.msig.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/weos.msig.contracts.md @ONLY )

target_compile_options( weos.msig PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
