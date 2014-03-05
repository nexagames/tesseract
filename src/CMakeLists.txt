include_directories(enet/include include engine game shared) 
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/${LIB_DIRECTORY}) 

# Server 
add_executable(tess_server WIN32 
	shared/crypto.cpp 
	shared/stream.cpp
	shared/tools.cpp 
	engine/command.cpp 
	engine/server.cpp 
	engine/worldio.cpp 
	game/entities.cpp 
	game/server.cpp
	vcpp/tesseract.rc)
set_target_properties(tess_server PROPERTIES COMPILE_FLAGS -DSTANDALONE)
set_target_properties(tess_server PROPERTIES RUNTIME_OUTPUT_DIRECTORY  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tess_server PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tess_server PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
set_target_properties(tess_server PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELWITHDEBINFO ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
target_link_libraries(tess_server enet zdll ws2_32 winmm)

# Server 
add_executable(tess_master 
	shared/crypto.cpp
	shared/stream.cpp
	shared/tools.cpp
	engine/command.cpp
	engine/master.cpp
	vcpp/tesseract.rc)
set_target_properties(tess_master PROPERTIES COMPILE_FLAGS -DSTANDALONE)
set_target_properties(tess_master PROPERTIES RUNTIME_OUTPUT_DIRECTORY  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tess_master PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tess_master PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
set_target_properties(tess_master PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELWITHDEBINFO ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
target_link_libraries(tess_master enet zdll ws2_32 winmm)

# Client
add_executable(tesseract WIN32
	shared/crypto.cpp
	shared/geom.cpp
	shared/glemu.cpp
	shared/stream.cpp
	shared/tools.cpp
	shared/zip.cpp
	engine/aa.cpp
	engine/bih.cpp
	engine/blend.cpp
	engine/client.cpp
	engine/command.cpp
	engine/console.cpp
	engine/decal.cpp
	engine/dynlight.cpp
	engine/grass.cpp
	engine/light.cpp
	engine/main.cpp
	engine/material.cpp
	engine/menus.cpp
	engine/movie.cpp
	engine/normal.cpp
	engine/octa.cpp
	engine/octaedit.cpp
	engine/octarender.cpp
	engine/ovr.cpp
	engine/physics.cpp
	engine/pvs.cpp
	engine/rendergl.cpp
	engine/renderlights.cpp
	engine/rendermodel.cpp
	engine/renderparticles.cpp
	engine/rendersky.cpp
	engine/rendertext.cpp
	engine/renderva.cpp
	engine/server.cpp
	engine/serverbrowser.cpp
	engine/shader.cpp
	engine/sound.cpp
	engine/texture.cpp
	engine/ui.cpp
	engine/water.cpp
	engine/world.cpp
	engine/worldio.cpp
	game/ai.cpp
	game/client.cpp
	game/entities.cpp
	game/game.cpp
	game/render.cpp
	game/scoreboard.cpp
	game/server.cpp
	game/waypoint.cpp
	game/weapon.cpp
	vcpp/tesseract.rc)
set_target_properties(tesseract PROPERTIES RUNTIME_OUTPUT_DIRECTORY  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tesseract PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG  ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY})
set_target_properties(tesseract PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
set_target_properties(tesseract PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELWITHDEBINFO ${CMAKE_SOURCE_DIR}/${BIN_DIRECTORY}) 
target_link_libraries (tesseract SDL2 SDL2_image SDL2_mixer opengl32 enet zdll ws2_32 winmm)	