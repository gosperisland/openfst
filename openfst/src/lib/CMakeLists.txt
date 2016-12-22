cmake_minimum_required(VERSION 2.6)
project (LibraryTest)



set(SOURCES_files_sources
    flags.cc
    fst.cc
    util.cc
    compat.cc
  )
set(SOURCES_files_include
  )

source_group(sources FILES ${SOURCES_files_sources})
source_group(include FILES ${SOURCES_files_include})
set(SOURCES
    ${SOURCES_files_sources}
    ${SOURCES_files_include}
)


if (CMAKE_COMPILER_IS_GNUCXX)
        

        set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x")
        if (NOT APPLE)
            add_definitions (-g -O2 -MT -Wall -MD -MP -MF -fPIC -DPIC) # todo: should we use CMAKE_C_FLAGS for these?
        endif ()

  
endif ()




include_directories(${BOOST_INCLUDE_DIRS})
#target_link_libraries(fst ${BOOST_LIBRARY_DIRS})


  include_directories(
    ./../include
  )



add_library(fst ${SOURCES})

