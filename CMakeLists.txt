cmake_minimum_required (VERSION 3.10.2)

##### PLUGIN NAME #####
set(pluginname gipTensorflow)


##### PLUGIN PATHS #####
set(PLUGIN_DIR ${PLUGINS_DIR}/${pluginname})
set(PLUGIN_LIBS_DIR ${PLUGIN_DIR}/libs)


##### PLUGIN SOURCES #####

file(GLOB_RECURSE SOURCES 
				"${PLUGIN_DIR}/src/*.cpp"
				"${PLUGIN_DIR}/libs/src/tensorflow/c/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/cc/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/tsl/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/tsl/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/core/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/core/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/core/*.py"
				"${PLUGIN_DIR}/libs/src/absl/*.c"
				"${PLUGIN_DIR}/libs/src/absl/*.cc"
				"${PLUGIN_DIR}/libs/src/absl/*.py"
				"${PLUGIN_DIR}/libs/src/googlemock/*.c"
				"${PLUGIN_DIR}/libs/src/googlemock/*.cc"
				"${PLUGIN_DIR}/libs/src/googlemock/*.py"
				"${PLUGIN_DIR}/libs/src/googletest/*.c"
				"${PLUGIN_DIR}/libs/src/googletest/*.cc"
				"${PLUGIN_DIR}/libs/src/googletest/*.py"
				
)
list(APPEND PLUGIN_SRCS ${SOURCES})


##### PLUGIN HEADERS #####
list(APPEND PLUGIN_INCLUDES
			${PLUGIN_DIR}/src
			${PLUGIN_LIBS_DIR}/include
			${PLUGIN_LIBS_DIR}/src
			${PLUGIN_LIBS_DIR}/src/absl
			${PLUGIN_LIBS_DIR}/src/googlemock
			${PLUGIN_LIBS_DIR}/src/googletest
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
