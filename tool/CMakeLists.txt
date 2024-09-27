include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)

add_clang_executable(clang-diff ClangDiff.cpp)
target_link_libraries(clang-diff clangASTMatchers clangBasic clangDiff
                      clangTooling)
target_include_directories(clang-diff PRIVATE ${LLMV_INCLUDE_DIRS})
