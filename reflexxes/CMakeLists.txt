cmake_minimum_required(VERSION 3.8)
project(reflexxes)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

include_directories(include/reflexxes)

add_library(reflexxes
# src/01_RMLPositionSampleApplication.cpp
# src/02_RMLPositionSampleApplication.cpp
# src/03_RMLPositionSampleApplication.cpp
# src/04_RMLVelocitySampleApplication.cpp
# src/05_RMLVelocitySampleApplication.cpp
# src/06_RMLVelocitySampleApplication.cpp
# src/07_RMLPositionSampleApplication.cpp
# src/08_RMLVelocitySampleApplication.cpp
src/ReflexxesAPI.cpp
src/TypeIIRMLCalculatePositionalExtrems.cpp
src/TypeIIRMLDecisions.cpp
src/TypeIIRMLDecisionTree1A.cpp
src/TypeIIRMLDecisionTree1B.cpp
src/TypeIIRMLDecisionTree1C.cpp
src/TypeIIRMLDecisionTree2.cpp
src/TypeIIRMLFallBackStrategy.cpp
src/TypeIIRMLIsPhaseSynchronizationPossible.cpp
src/TypeIIRMLPolynomial.cpp
src/TypeIIRMLPosition.cpp
src/TypeIIRMLQuicksort.cpp
src/TypeIIRMLSetupModifiedSelectionVector.cpp
src/TypeIIRMLStep1.cpp
src/TypeIIRMLStep1IntermediateProfiles.cpp
src/TypeIIRMLStep1Profiles.cpp
src/TypeIIRMLStep2.cpp
src/TypeIIRMLStep2IntermediateProfiles.cpp
src/TypeIIRMLStep2PhaseSynchronization.cpp
src/TypeIIRMLStep2Profiles.cpp
src/TypeIIRMLStep2WithoutSynchronization.cpp
src/TypeIIRMLStep3.cpp
src/TypeIIRMLVelocityCalculatePositionalExtrems.cpp
src/TypeIIRMLVelocity.cpp
src/TypeIIRMLVelocityFallBackStrategy.cpp
src/TypeIIRMLVelocityIsPhaseSynchronizationPossible.cpp
src/TypeIIRMLVelocityMethods.cpp
src/TypeIIRMLVelocitySetupPhaseSyncSelectionVector.cpp
)

install( TARGETS reflexxes DESTINATION lib )
install( DIRECTORY include/ DESTINATION include )


if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
