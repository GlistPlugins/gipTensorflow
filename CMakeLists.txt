cmake_minimum_required (VERSION 3.10.2)

##### PLUGIN NAME #####
set(pluginname gipTensorflow)


##### PLUGIN PATHS #####
set(PLUGIN_DIR ${PLUGINS_DIR}/${pluginname})
set(PLUGIN_LIBS_DIR ${PLUGIN_DIR}/libs)


##### PLUGIN SOURCES #####

file(GLOB_RECURSE SOURCES 
				"${PLUGIN_DIR}/src/*.cpp"
				"${PLUGIN_DIR}/libs/src/tensorflow/*.cpp"
)
list(APPEND PLUGIN_SRCS ${SOURCES})


##### PLUGIN HEADERS #####
list(APPEND PLUGIN_INCLUDES
			${PLUGIN_DIR}/src
			${PLUGIN_LIBS_DIR}/include
			${PLUGIN_LIBS_DIR}/src/tensorflow/c
			${PLUGIN_LIBS_DIR}/src/tensorflow/cc
)

##### PLUGIN DEPENDENCY LOCATIONS (IF ANY) #####
if(WIN32)
	list(APPEND PLUGIN_LINKDIRS
				${PLUGIN_LIBS_DIR}/lib/win32
				${PLUGIN_LIBS_DIR}/bin
	)
	
	#set(PLUGIN_LIBDIRS ${PLUGIN_LIBS_DIR}/lib/win32)
	list(APPEND PLUGIN_LIBDIRS
				${PLUGIN_LIBS_DIR}/lib/win32
	)
elseif(LINUX)
	#Linux libs here
elseif(APPLE)
	#Macos libs here
endif(WIN32)


##### PLUGIN DEPENDENCY LINKING (IF ANY) #####					
if(WIN32)
	list(APPEND PLUGIN_LINKLIBS
				#Lib names
	)
elseif(LINUX)
	list(APPEND PLUGIN_LINKLIBS
				#Lib names
	)
elseif(APPLE)
	list(APPEND PLUGIN_LINKLIBS
				#Lib names
	)
endif(WIN32)
