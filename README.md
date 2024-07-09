# FIRO ROS2 Workspace

This is a opinionated ROS2 workspace based on another great [vscode_ros2_workspace](https://github.com/athackst/vscode_ros2_workspace) template. 

The main differences from original [vscode_ros2_workspace](https://github.com/athackst/vscode_ros2_workspace) comes to using:
- clang-format instead of uncrustify
- cmake-format for CMake formatting
- clangd as c++ language server (code completion, navigation, etc.)
- clang-tidy and cppcheck for static analysis
- ccache for speeding up compilation
- native vscode repository detection with scan depth increased to 2 instead of submodules and Vcstool


This workspace is a work in progress and may still be improved. Detailed instructions on how to use it will be added soon, but for now you can follow the instructions from the original [vscode_ros2_workspace](https://github.com/athackst/vscode_ros2_workspace) template.