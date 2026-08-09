# ReduxLib

The current version of ReduxLib for SystemCore is **2027.0.0-alpha-6.**

It supports WPILib alpha version **2027.0.0-alpha-5+**.

Currently, this is more or less identical to v2026.1.2, but future versions may change this.
For more details, also see our [releases page](https://github.com/Redux-Robotics/canandrepo-public/releases)

## Install

### JSON

```txt
https://frcsdk.reduxrobotics.com/ReduxLib_2027.json
```

### Offline install zip

Extract this into the root of your `wpilib/2027_alpha5` directory.

This is in `~/wpilib/2027_alpha5` on Linux/Mac, and on Windows it is typically in `C:\Users\Public\wpilib\2027_alpha5`

[ReduxLib-offline-v2027.0.0-alpha-6.zip](https://frcsdk.reduxrobotics.com/offline/ReduxLib-offline-v2027.0.0-alpha-6.zip)

## CAN ID configuration

Just like v2026, the ReduxLib configurator will be available at `http://[insert SystemCore address here]:7244/`, 
e.g. [http://robot.local:7244](http://robot.local:7244).

It should function exactly the same as it did in v2026.

## Usage

By default, if no bus is specified, devices will use SocketCAN bus **`can_s0`**.

An alternate SocketCAN bus can be passed in with an index: 

```java
// use can_s4 instead
Canandgyro gyro = new Canandgyro(0, 4);
```

Or, you can use a bus specifier string directly:

```java
// MotionCore port 2
Canandgyro gyro = new Canandgyro(0, "socketcan:can_d2");
```

## Known issues

* The CAN ID configurator orders the buses in a non-logical fashion. 

## Changelog

### ReduxLib v2027.0.0-alpha-6

- [General] Support WPILib v2027.0.0-alpha-6
- [General] Rebase everything on v2026.1.2

### ReduxLib v2027.0.0-alpha-2

- [General] Add support for WPILib v2027.0.0-alpha-2
- [General] Add rewritten driver backend
- [Canandgyro] `setYaw` and `setPose` now retry up to 5 times by default.
