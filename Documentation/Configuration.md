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

3. On the following page the steppers are configured. The direction is dependent of how you plug the steppers into the Duet so for now just leave them all as Forwards, this can be changed anytime from the web interface or by reversing the plug on the steppers. Note: never insert or remove a stepper while the Duet is powered or you risk frying the driver!