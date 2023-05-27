cmake_minimum_required(VERSION 3.21)
project(LUFSMeter)


# Create the shared library target
add_library(LUFSMeter SHARED 
    Ebu128LoudnessMeter.h
    Ebu128LoudnessMeter.cpp
    MacrosAndJuceHeaders.h
    filters/SecondOrderIIRFilter.cpp
    filters/SecondOrderIIRFilter.h
)

# Include directories
target_include_directories(LUFSMeter 
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/filters
)

target_link_libraries(LUFSMeter 
    PUBLIC juce::juce_core)