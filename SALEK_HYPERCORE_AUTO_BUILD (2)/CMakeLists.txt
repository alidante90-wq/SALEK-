cmake_minimum_required(VERSION 3.22)
project(SalekHypercore VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

# JUCE is downloaded automatically during configuration when internet is available.
FetchContent_Declare(
    JUCE
    GIT_REPOSITORY https://github.com/juce-framework/JUCE.git
    GIT_TAG 8.0.12
    GIT_SHALLOW TRUE
)
FetchContent_MakeAvailable(JUCE)

juce_add_plugin(SalekHypercore
    COMPANY_NAME "SALEK HighTech"
    BUNDLE_ID "com.salekhightech.hypercore"
    PLUGIN_MANUFACTURER_CODE SlkH
    PLUGIN_CODE HyC1
    FORMATS VST3 Standalone
    PRODUCT_NAME "SALEK HYPERCORE"
    IS_SYNTH TRUE
    NEEDS_MIDI_INPUT TRUE
    NEEDS_MIDI_OUTPUT FALSE
    COPY_PLUGIN_AFTER_BUILD TRUE
)

target_sources(SalekHypercore PRIVATE
    Source/PluginProcessor.cpp
    Source/PluginProcessor.h
    Source/PluginEditor.cpp
    Source/PluginEditor.h
    Source/Engine/HyperVoice.cpp
    Source/Engine/HyperVoice.h
    Source/Engine/HyperSound.h
)

target_compile_definitions(SalekHypercore PRIVATE
    JUCE_WEB_BROWSER=0
    JUCE_USE_CURL=0
    JUCE_VST3_CAN_REPLACE_VST2=0
)

target_link_libraries(SalekHypercore PRIVATE
    juce::juce_audio_utils
    juce::juce_dsp
)
