!!! important
    You should have SUMMIT setup before running. To install SUMMIT, follow the [setting up steps](../setting_up).

## Running SUMMIT
Open a terminal in the folder where SUMMIT was extracted, and run `./CarleUE4.sh` to start the simulator. A window will open, containing an empty map. 

!!! note
    If you get an X Error when running the simulator, try `./CarlaUE4.sh -opengl` instead.

The simulator is now running as a server, waiting for client apps to connect and to interact (e.g. spawning map objects dynamically, simulating a crowd, etc.) with it. To move around, use the mouse and WASD keys (while clicking). 

## What's next?

Check out the tutorials on this website on how to use the various features of SUMMIT. For example, you can start by [spawning maps](../../tutorials/loading_and_spawning_maps) and [simulating traffic](../../tutorials/simulating_traffic). If you want to control your own agent, you can check out how to [navigate roads and sidewalks](../../tutorials/using_roads_and_sidewalks).
