<h1> Running SUMMIT </h1>

## Launching simulator

!!! important
    You should have SUMMIT setup before running. To install SUMMIT, follow the [setting up steps](../setting_up).

Open a terminal in the folder where SUMMIT was extracted, and run `./CarleUE4.sh` to start the simulator. A window will open, containing an empty map.

!!! note
    If you get an X Error when running the simulator, try `./CarlaUE4.sh -opengl` instead.

The simulator is now running as a server, waiting for client apps to connect and to interact (e.g. spawning map objects dynamically, simulating a crowd, etc.) with it.

## Running an example scenario

!!! note
    If you get `AttributeError`s or other unexpected errors when running the scripts in this section, you may need to add the `*.egg` files under `<summit_root>/PythonAPI/dist/` to your `PYTHON_PATH`.

Here, we provide a walkthrough of how to use SUMMIT to run a simple scenario, to showcase the various features of SUMMIT.

You will spawn a map of Meskel Square, one of SUMMIT's [built-in maps](../../references/summit_map_library/). Next, you will spawn a heterogeneous crowd on the map. Finally, you will run a sample agent, which attempts to navigate through the crowd.

Firstly, spawn the Meskel Square map using the built-in `spawn_meshes.py` and `spawn_imagery.py` scripts. This will spawn the meshes and imagery relevant to Meskel Square:
```bash
<summit_root>/PythonAPI/examples/spawn_meshes.py --dataset meskel_square
<summit_root>/PythonAPI/examples/spawn_imagery.py --dataset meskel_square
```

Secondly, spawn a heterogeneous crowd on the map using the built-in `gamma_crowd.py` script. This will simulate a heterogeneous traffic on the spawned map:
```bash
<summit_root>/PythonAPI/examples/gamma_crowd.py --dataset meskel_square
```

Finally, run the built-in sample `meskel_square_ego_vehicle.py` script. This will spawn an agent that navigates through the crowd.
```bash
<summit_root>/PythonAPI/examples/meskel_square_ego_vehicle.py
```


## What's next?
To get started writing your own scripts to interact with SUMMIT, you may step through the programming tutorials:

* [Load and spawn existing maps](../../tutorials/loading_and_spawning_maps/)
* [Using roads and sidewalks](../../tutorials/using_roads_and_sidewalks/)

To learn how to prepare your own maps, or to read more about how to use the built-in traffic simulator, you may step through the map tutorials:

* [Prepare new maps](../../tutorials/preparing_maps/)
* [Simulate traffic in new maps](../../tutorials/simulating_traffic/)
* [Configuring the simulation](../../tutorials/configure_the_simulation/)

To use the expert planner, check out our [Context-POMDP repository](https://github.com/AdaCompNUS/context-pomdp.git).
