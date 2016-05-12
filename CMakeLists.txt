PROJECT (hlslparser)

SET (PROJECT_SOURCES
    src/CodeWriter.cpp
    src/GLSLGenerator.cpp
    src/HLSLGenerator.cpp
    src/HLSLParser.cpp
    src/HLSLTokenizer.cpp
    src/HLSLTree.cpp
    src/Main.cpp
    src/Engine.cpp
    )

SET (PROJECT_INCLUDES
    ) 

SET (ALL_SOURCES ${PROJECT_SOURCES} ${PROJECT_INCLUDES})

# Create the library
ADD_EXECUTABLE (${PROJECT_NAME} ${ALL_SOURCES} ${PROJECT_INCLUDES})

# Add Debug or Release UWP Runtime
IF (TARGET_UWP)
TARGET_LINK_LIBRARIES(${PROJECT_NAME} debug vccorlibd)
TARGET_LINK_LIBRARIES(${PROJECT_NAME} optimized vccorlib)
ENDIF()

