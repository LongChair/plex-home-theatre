add_subdirectory(VideoShaders)
find_all_sources(. videorenderers_SRCS)

list(REMOVE_ITEM videorenderers_SRCS ./LinuxRendererGL.cpp)

if(NOT WIN32)
  list(REMOVE_ITEM videorenderers_SRCS ./WinRenderer.cpp)
  list(REMOVE_ITEM videorenderers_SRCS ./OverlayRendererDX.cpp)
else()
  list(REMOVE_ITEM videorenderers_SRCS ./LinuxRendererGL.cpp)
endif()
add_sources(${videorenderers_SRCS})
