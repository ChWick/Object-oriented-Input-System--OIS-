cmake_minimum_required(VERSION 2.8)

set(OIS_LIB_NAME OIS)

include_directories(includes)

file(GLOB_RECURSE OIS_INCLUDE_FILES
  includes/OIS.h
  includes/OISConfig.h
  includes/OISEffect.h
  includes/OISEvents.h
  includes/OISException.h
  includes/OISFactoryCreator.h
  includes/OISForceFeedback.h
  includes/OISInputManager.h
  includes/OISInterface.h
  includes/OISJoyStick.h
  includes/OISKeyboard.h
  includes/OISMouse.h
  includes/OISMultiTouch.h
  includes/OISObject.h
  includes/OISPrereqs.h
)

ADD_LIBRARY(${OIS_LIB_NAME} STATIC
  src/OISEffect.cpp
  src/OISException.cpp
  src/OISForceFeedback.cpp
  src/OISInputManager.cpp
  src/OISJoyStick.cpp
  src/OISKeyboard.cpp
  src/OISObject.cpp)


install(TARGETS ${OIS_LIB_NAME} 
   ARCHIVE
   DESTINATION lib
   COMPONENT libraries)

install(FILES ${OIS_INCLUDE_FILES} 
   DESTINATION include
   COMPONENT headers)