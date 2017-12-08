set(TEMPLATES_DIR ${PROJECT_SOURCE_DIR}/Templates)

add_library(NLTemplate NLTemplate.cpp NLTemplate.h)

add_executable(demo test.cpp)
target_link_libraries(demo NLTemplate)
target_compile_options(demo PUBLIC -g)
add_custom_command(TARGET demo POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E copy_directory
	${TEMPLATES_DIR} $<TARGET_FILE_DIR:demo>
)

add_test(demoTest demo ${TEMPLATES_DIR}/test.txt ${TEMPLATES_DIR}/testheader.txt)

add_definitions(-DTEMPLATES_DIR="${TEMPLATES_DIR}")