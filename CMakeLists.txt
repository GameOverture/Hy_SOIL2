project(soil2)

set(SOIL2_SOURCE_FILES
	src/SOIL2/image_DXT.c                                                          
	src/SOIL2/image_DXT.h                                                          
	src/SOIL2/image_helper.c                                                       
	src/SOIL2/image_helper.h                                                       
	src/SOIL2/jo_jpeg.h                                                            
	src/SOIL2/pkm_helper.h                                                         
	src/SOIL2/pvr_helper.h                                                         
	src/SOIL2/SOIL2.c                                                              
	src/SOIL2/SOIL2.h                                                              
	src/SOIL2/stbi_DDS.h                                                           
	src/SOIL2/stbi_DDS_c.h                                                         
	src/SOIL2/stbi_ext.h                                                           
	src/SOIL2/stbi_ext_c.h                                                         
	src/SOIL2/stbi_pkm.h                                                           
	src/SOIL2/stbi_pkm_c.h                                                         
	src/SOIL2/stbi_pvr.h                                                           
	src/SOIL2/stbi_pvr_c.h                                                         
	src/SOIL2/stb_image.h                                                          
	src/SOIL2/stb_image_write.h                                                    
	src/SOIL2/wfETC.c                                                              
	src/SOIL2/wfETC.h)

add_library(${PROJECT_NAME} STATIC ${SOIL2_SOURCE_FILES})
target_include_directories(${PROJECT_NAME} PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2")
target_include_directories(${PROJECT_NAME} PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/../glad/include")
set_target_properties(${PROJECT_NAME} PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARD_REQUIRED YES
	CXX_EXTENSIONS NO)

set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER "Engine Libs")

if (MSVC)
	target_compile_definitions(${PROJECT_NAME} PUBLIC _CRT_SECURE_NO_WARNINGS)
endif()
