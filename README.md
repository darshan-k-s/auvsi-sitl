# AUVSI SITL

### Gazebo SITL simulation for AUVSI
<br>

### Stack used:
Drone firmware: px4
Protocol: MAVLink
Ground station: MAVSDK

Go through the [Getting started file](./gettingStarted.md) for setting up the SITL env.


### Directory structure:
There is only a part of the MAVSDK library in this repository. You need to setup the whole sim env and only use this for reference.

I have only uploaded the `examples\takeoff_land` and `examples\fly_mission` .

```
------- MAVSDK (The whole MAVSDK library)
      |
      |--- /build
      |--- /debian
      |---  .
            .
            .
      |--- /examples (Example MAVSDK apps included in the library)
         |
         |--- (Only listing some examples)
              .
              .
         |--- /fly_mission (Sample waypoint nav mission uploader)
         |--- /fly_qgc_mission(Import mission items from QGC plan)
         |--- /geofence_inclusion(Include geofence in the mission)
         |--- /manual_control(Switching to manual control)
         |--- /takeoff_land(Take off and land mission to test SITL setup. I've added some comments for understanding)

```


