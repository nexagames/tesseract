cmake_minimum_required (VERSION 2.8) 
project (Tesseract) 

if(${CMAKE_CL_64})
 	set(BIN_DIRECTORY bin64)
else()
	set(BIN_DIRECTORY bin)	
endif()

if (${CMAKE_CL_64})
 	set(LIB_DIRECTORY lib64)
else()
	set(LIB_DIRECTORY lib)	
endif()

add_subdirectory (src)