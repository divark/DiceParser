set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -fno-permissive -pedantic -Wall -Wextra")
set(CMAKE_AUTOMOC ON)
find_package(Qt5Test REQUIRED)

set(test_source testnode.cpp tst_dice.cpp)

add_executable(test_dice ${test_source} ${dice_sources})

target_include_directories(test_dice PRIVATE ../../include)

target_link_libraries(test_dice Qt5::Test)
add_test(tst_diceparser test_dice)
