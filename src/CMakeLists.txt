file(GLOB_RECURSE FCL_SOURCE_CODE ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)
if(FCL_STATIC_LIBRARY)
  add_library(${PROJECT_NAME} STATIC ${FCL_SOURCE_CODE})
else()
  add_library(${PROJECT_NAME} SHARED ${FCL_SOURCE_CODE})
endif()

target_link_libraries(${PROJECT_NAME} ${CCD_LIBRARIES} ${OCTOMAP_LIBRARIES} ${Boost_LIBRARIES})

install(TARGETS ${PROJECT_NAME} ARCHIVE DESTINATION lib/ LIBRARY DESTINATION lib/)
