if (WHISPER_SDL2)
    # voice-agent
    set(TARGET whisper-voice-agent)
    add_executable(${TARGET} voice-agent.cpp)

    include(DefaultTargetOptions)

    target_link_libraries(${TARGET} PRIVATE common common-sdl whisper ${CMAKE_THREAD_LIBS_INIT})
    
    install(TARGETS ${TARGET} RUNTIME)
endif ()
