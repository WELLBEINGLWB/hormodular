# Hormodular main executables ################################################################
# Evolve gaits for a robot
add_executable( evolve-gaits evolve_gaits.cpp ModularRobotEvalOp.cpp )
set_target_properties(evolve-gaits PROPERTIES COMPILE_FLAGS "${CMAKE_CXX_FLAGS}")
set_target_properties(evolve-gaits PROPERTIES LINK_FLAGS "${ECF_LINK_FLAGS}")
target_link_libraries(evolve-gaits ConfigParser Oscillator ModularRobotInterface ${ECF_LINK_FLAGS})

# Evaluate a given individual (simulated robot)
add_executable( evaluate-gaits-sim evaluate_gaits_sim.cpp )
set_target_properties(evaluate-gaits-sim PROPERTIES COMPILE_FLAGS "${CMAKE_CXX_FLAGS}")
set_target_properties(evaluate-gaits-sim PROPERTIES LINK_FLAGS "${ECF_LINK_FLAGS}")
target_link_libraries(evaluate-gaits-sim ModularRobot )

# Evaluate a given individual with controller (simulated robot)
add_executable( evaluate-controller-sim evaluate_controller_sim.cpp )
set_target_properties(evaluate-controller-sim PROPERTIES COMPILE_FLAGS "${CMAKE_CXX_FLAGS}")
set_target_properties(evaluate-controller-sim PROPERTIES LINK_FLAGS "${ECF_LINK_FLAGS}")
target_link_libraries(evaluate-controller-sim ModularRobot )

# Evaluate a given individual (serial robot)
add_executable( evaluate-gaits-serial evaluate_gaits_serial.cpp )
set_target_properties(evaluate-gaits-serial PROPERTIES COMPILE_FLAGS "${CMAKE_CXX_FLAGS}")
set_target_properties(evaluate-gaits-serial PROPERTIES LINK_FLAGS "${ECF_LINK_FLAGS}")
target_link_libraries(evaluate-gaits-serial ModularRobot )
