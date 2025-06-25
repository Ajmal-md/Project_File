cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
#
# Include our basic CMake script
#
include(BuildUtils)
#
# Set the project name: "_NAME_AUTO_" will use the folder name
#
set_project_name("_NAME_AUTO_")
#
# List with modules we depend on
#
add_module_dependencies(
    "frameserver"
    "encodermtd"
    "fsfrontend"
    "fslogger"
    "fssettings"
    "memallocator"
    "fsmsg"
    "imgmtd"
)
#
# Include extra directories relative to the module source folder
#
include_module_directories(
	"${CMAKE_BINARY_DIR}/../../2_install/install_folder/includes"
)

#
# List of public module header files, relative to the module source folder
#
add_public_headers()
#
# List of public module header files, relative to the module source folder
#
add_export_headers()
#
# List of source files, relative to the module source folder
#
add_sources(
	"consumerclient.cpp"
)
add_libs_to_exe()
#
# Build and install library
#
install_module_exe()
