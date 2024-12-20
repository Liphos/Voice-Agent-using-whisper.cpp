if (WHISPER_SDL2)
    # voice-agent
    set(TARGET voice-agent)
    add_executable(${TARGET} voice-agent.cpp)

    include(DefaultTargetOptions)

    target_link_libraries(${TARGET} PRIVATE common common-sdl whisper ${CMAKE_THREAD_LIBS_INIT})
endif ()
