## Configuration for Duet
This section will cover the initial configuration of the Duet controller for the printer, for problems and tuning go [here](Documentation/Issues.md) and for setting up a new Duet [here](https://duet3d.dozuki.com/Guide/1.+Getting+Connected+to+your+Duet/7).

To start we use the [RepRap Config Tool](https://configurator.reprapfirmware.org/Start) to generate the initial configuration file. 



1. First start by selecting the custom configuration option and click next.
2. On this page enable the Read config-override.g option and make sure to select the CoreXY Geometry option. For the axis min and max see the following table: 

| Axis  | Position |
| :--:  | :------: |
| X Min |    0     |
| X Max |   330    |
| Y Min |   -40    |
| Y Max |   400    |
| Z Min |    0     |
| Z Max |   550    |

3. On the following page the steppers are configured. The direction is dependent of how you plug the steppers into the Duet so for now just leave them all as Forwards, this can be changed anytime from the web interface or by reversing the plug on the steppers. Note: never insert or remove a stepper while the Duet is powered or you risk frying the driver! For this section I am going to assume 1.8* steppers for the X, Y, and Z, a 0.9* stepper for the E, and x16 microstepping interpolated to x256. The settings are as follows:

| Drive | Steps per mm | Max Speed Change (mm/s) | Max Speed (mm/s) | Acceleration (mm/s<sup>2</sup>) | Motor Current (mA) | Motor Driver |
| :---: | :----------: | :---------------------: | :--------------: | :-----------------------------: | :----------------: | :----------: |
|   X   |     80       |            10           |        250       |               500               |        1200        |     0 (X)    |
|   Y   |     80       |            10           |        250       |               500               |        1200        |     1 (Y)    |
|   Z   |     100      |            0.2          |        10        |               20                |        1800        |     2 (Z)    |
|   E   |     837      |            2            |        20        |               250               |        1000        |     3 (E0)   |