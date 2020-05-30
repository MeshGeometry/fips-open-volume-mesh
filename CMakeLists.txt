if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup()
    fips_project(fips-open-volume-mesh)
endif()

if ((FIPS_MACOS OR FIPS_WINDOWS OR FIPS_LINUX) AND NOT (FIPS_RASPBERRYPI OR FIPS_UWP))

# not sure about this

add_subdirectory(OpenVolumeMesh/OpenVolumeMesh)

endif()

if (NOT FIPS_IMPORT)
    fips_finish()
endif()