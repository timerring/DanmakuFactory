cmake_minimum_required(VERSION 3.5)

project(DanmakuFactory C)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

if (MSVC)
        add_compile_options(/wd4819)
        add_compile_options(/wd4996)
endif()

add_executable (DanmakuFactory JsonFile.c main.c XmlFile.c
                AssFile/AssFile.c AssFile/AssStringProcessing.c Config/Config.c
                List/DanmakuFactoryList.c String/DanmakuFactoryString.c TemplateFile/TemplateFile.c)

install(TARGETS DanmakuFactory
        CONFIGURATIONS Release
        RUNTIME DESTINATION ${CMAKE_SOURCE_DIR}/bin)
