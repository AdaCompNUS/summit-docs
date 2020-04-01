!!! important
    You should have SUMMIT setup before running. To install SUMMIT, follow the [setting up steps](../setting_up).

## Running SUMMIT
Open a terminal in the folder where SUMMIT was extracted, and run `./CarleUE4.sh` to start the simulator. A window will open, containing an empty map. 

!!! note
    If you get an X Error when running the simulator, try `./CarlaUE4.sh -opengl` instead.

The simulator is now running as a server, waiting for client apps to connect and to interact (e.g. spawning map objects dynamically, simulating a crowd, etc.) with it. To move around, use the mouse and WASD keys (while clicking). 

## What's next?

Check out the tutorials on this website on how to use the various features of SUMMIT. You can also check out our [Context-POMDP repository](https://github.com/AdaCompNUS/context-pomdp), which does online POMDP planning on an ego-vehicle in SUMMIT.
