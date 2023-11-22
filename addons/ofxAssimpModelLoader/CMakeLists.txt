set(ADDON "ofxAssimpModelLoader")
set(ADDON_DIR "${OF_DIR}/addons/${ADDON}")
set(ADDON_SRC_DIR "${ADDON_DIR}/src")

message("Adding ${ADDON_DIR}")

include_directories(${OF_DIR}/libs/openFrameworks/types)
include_directories(${OF_DIR}/libs/openFrameworks/video)
include_directories(${ADDON_DIR}/src)

add_library(ofxAssimpModelLoader 
   ${ADDON_SRC_DIR}/ofxAssimpAnimation.cpp
   ${ADDON_SRC_DIR}/ofxAssimpMeshHelper.cpp
   ${ADDON_SRC_DIR}/ofxAssimpModelLoader.cpp
   ${ADDON_SRC_DIR}/ofxAssimpTexture.cpp
   ${OF_DIR}/libs/openFrameworks/gl/ofMaterial.cpp
   ${OF_DIR}/libs/openFrameworks/math/ofMatrix4x4.cpp
   ${OF_DIR}/libs/openFrameworks/math/ofQuaternion.cpp
)

link_directories(/usr/lib)
target_link_libraries(openFrameworks INTERFACE ofxAssimpModelLoader assimp)