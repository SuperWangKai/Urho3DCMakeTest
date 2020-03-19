# Project for CMake testing in Urho3D


## 1 Build on Windows

### 1.1 Prepare projects
* Clone official Urho3D project under the same parent directory. You should see `Urho3DCMakeTest` and `Urho3D` are in the same folder.

### 1.2 Build Urho3D project
* In the Urho3D directory, generate Visual Studio solution of Urho3D with command line like `script\cmake_vs2019.bat BUILD_vs2019 -DURHO3D_64BIT=1 -DURHO3D_LUA=0 -DURHO3D_D3D11=1`.
* Open generated Visual Studio solution in BUILD_vs2019 and build Urho3D.

### 1.3 Build Urho3DCMakeTest project
* Set `URHO3D_HOME` environment variable to the path of folder `BUILD_vs2019` of Urho3D
* `mkdir BUILD_vs2019` inside Urho3DCMakeTest.
* Generate the project with CMake using commandline like `cd BUILD_vs2019` and `cmake ..`
* Now you can see the Visual Studio solution is in BUILD_vs2019. You can build it with Visual Studio and run the sample.




   