https://qa.fmod.com/t/can-we-commit-the-fmod-api-to-our-integration-libraries-on-github/15751/9

FMOD can be included in your project's CMakeLists.txt by:

add_subdirectory("<FMOD-directory>" FMOD)

add_custom_command(TARGET <TARGET> POST_BUILD
  COMMAND ${CMAKE_COMMAND} -E copy_if_different
      $<TARGET_FILE:FMOD>
      $<TARGET_FILE_DIR:<TARGET>>
)