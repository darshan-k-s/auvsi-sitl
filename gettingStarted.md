# Few basic commands and setup

### Stack: px4 + MAVSDK + Gazebo
<br>



### <ins>px4:</ins>

- Initial setup:

    [Firmware setup on Linux](https://dev.px4.io/v1.10_noredirect/en/setup/dev_env_linux_ubuntu.html#sim_nuttx).

    [Gazebo dependencies](https://docs.px4.io/master/en/dev_setup/dev_env_linux_ubuntu.html#gazebo-jmavsim-and-nuttx-pixhawk-targets).

    [QGC](https://docs.qgroundcontrol.com/master/en/getting_started/download_and_install.html) - Install anywhere, automatically gets connected to sim through UDP port.

    [Quickstart | Docs](https://dev.px4.io/v1.10_noredirect/en/simulation/gazebo.html).

    [More on Gazebo sim](https://docs.px4.io/master/en/simulation/gazebo.html).

---


- Starting SITL sim(px4):
```bash
# For default quadcopter - iris
make px4_sitl gazebo

# For other models
make px4_sitl gazebo_modelName
# Eg: 
# For quadcopter - solo
make px4_sitl gazebo_solo
#For hexacopter- typhoon:
make px4_sitl gazebo_typhoon_h480

```
Rebuilding SITL:
```bash
make clean
# Then build your SITL
```


- Setting spawn locations:
```bash
export PX4_HOME_LAT=47.398170327054473
export PX4_HOME_LON=8.5456490218639658
export PX4_HOME_ALT=28.5
```
The `export` command is used to set environment variables.


- Changing simulation speed:
```bash
export PX4_SIM_SPEED_FACTOR=2
```

- Video streaming:

Open issue for Ubuntu 18.04.

Need to have pre-installed Gstreamer 1.0. We watch the livestream on QGC through `UDP Port:5600`. 


- Loading a specific world:

```bash
export PX4_SITL_WORLD=worldName
# worldName excluding the extension
```

[List of pre-built worlds](https://docs.px4.io/master/en/simulation/gazebo_worlds.html).


---


### <ins>MAVSDK:</ins>

[Quickstart](https://mavsdk.mavlink.io/main/en/cpp/quickstart.html).


- Building our file:
First navigate to the directory.
```bash
mkdir build && cd build
cmake ..
make
```

- Running the exe:
```bash
# Move to the parent dir first
build/takeoff_and_land udp://:14540
```





