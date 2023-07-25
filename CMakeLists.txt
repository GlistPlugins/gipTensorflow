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
				"${PLUGIN_DIR}/libs/src/tensorflow/c/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/cc/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/cc/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/core/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/core/*.cc"
				"${PLUGIN_DIR}/libs/src/tensorflow/tsl/*.c"
				"${PLUGIN_DIR}/libs/src/tensorflow/tsl/*.cc"
				"${PLUGIN_DIR}/libs/src/third_party/absl/*.c"
				"${PLUGIN_DIR}/libs/src/third_party/absl/*.cc"
				"${PLUGIN_DIR}/libs/src/third_party/googlemock/*.c"
				"${PLUGIN_DIR}/libs/src/third_party/googlemock/*.cc"
				"${PLUGIN_DIR}/libs/src/third_party/googletest/*.c"
				"${PLUGIN_DIR}/libs/src/third_party/googletest/*.cc"
				"${PLUGIN_DIR}/libs/src/third_party/benchmark/*.c"
				"${PLUGIN_DIR}/libs/src/third_party/benchmark/*.cc"
				"${PLUGIN_DIR}/libs/src/third_party/eigen/*.cpp"							
)

list(APPEND PLUGIN_SRCS ${SOURCES})


##### PLUGIN HEADERS #####
list(APPEND PLUGIN_INCLUDES
            ${PLUGIN_DIR}/src
            ${PLUGIN_LIBS_DIR}/include
            ${PLUGIN_LIBS_DIR}/src
            ${PLUGIN_LIBS_DIR}/src/tensorflow
            ${PLUGIN_LIBS_DIR}/src/third_party
            ${PLUGIN_LIBS_DIR}/src/third_party/eigen
            ${PLUGIN_LIBS_DIR}/src/third_party/googlemock/include
            ${PLUGIN_LIBS_DIR}/src/third_party/googletest/include
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
