add_contract(weos.bios weos.bios ${CMAKE_CURRENT_SOURCE_DIR}/src/weos.bios.cpp)

target_include_directories(weos.bios
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(weos.bios
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/weos.bios.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/weos.bios.contracts.md @ONLY )

target_compile_options( weos.bios PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
