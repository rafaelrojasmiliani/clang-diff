project(clangdiff)
cmake_policy(SET CMP0057 NEW)

set(LLVM_LINK_COMPONENTS suport)
find_package(Clang REQUIRED)
find_package(LLVM REQUIRED)

include("${LLVM_CMAKE_DIR}/AddLLVM.cmake")
include("${CLANG_CMAKE_DIR}/AddClang.cmake")

include_directories(${LLVM_INCLUDE_DIRS})
add_clang_library(
  clangDiff
  InfoTree.cpp
  LabelDictionary.cpp
  LblTree.cpp
  RTED.cpp
  LINK_LIBS
  clangAST
  clangASTMatchers
  clangBasic
  clangTooling)

add_subdirectory(tool)
