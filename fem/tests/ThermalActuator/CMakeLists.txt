IF(HAVE_UMFPACK OR HAVE_MUMPS)
  INCLUDE(test_macros)
  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

  CONFIGURE_FILE( thermal_actuator.sif thermal_actuator.sif COPYONLY)

  file(COPY ELMERSOLVER_STARTINFO actuator.msh DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

  ADD_ELMER_TEST(ThermalActuator)
ENDIF()
