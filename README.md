# Billy Jean Robot Libraries

A wrapper to Billy Jean custom libraries to ROS.

# Installing

On a good and blessed day, recursively clone this repo to your catkin workspace `src` folder

```
$ git clone --recursive https://github.com/filRocha/bj_libraries
```

and then compile your workspace

```
$ catkin build 
```
 **Note:** I have tested on `catkin build` compiling tool. The `catkin_make` should also work


# Using

If well compiled, add to your package's:

- `package.xml`:
```
<build_depend>bj_libraries</build_depend>
...
<build_export_depend>bj_libraries</build_export_depend>
...
<exec_depend>bj_libraries</exec_depend>
```

- and `CMakeLists`:
```
find_package(catkin REQUIRED COMPONENTS
  ...
  bj_libraries
)
```

You then shall be able to add the libraries to your node with
```
#include <lib_quaternion/Quaternion.h>
#include <lib_dualquaternion/DualQuaternion.h>
```

Have a great life! :)
