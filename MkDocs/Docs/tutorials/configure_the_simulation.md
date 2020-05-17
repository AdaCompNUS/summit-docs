<h1>Configuring the Simulation</h1>

## Changing the crowd setting

Properties of the simulated crowd can be controled via the arguments in `<summit_root>/PythonAPI/examples/gamma_crowd.py`. Important ones include:

* **--num-car**: the target number of car-like vehicles to be maitained in the scene.
* **--num-bike**: the target number of bikes and motorcycles to be maitained in the scene.
* **--num-pedestrian**: the target number of walkers to be maitained in the scene.
* **--speed-car**: the preferred speed of car-like vehicles. A uniform noise between [-0.5,0.5] will be added.
* **--speed-bike**: the preferred speed of bikes and motorcycles. A uniform noise between [-0.5,0.5] will be added.
* **--speed-pedestrian**: the preferred speed of walkers. A uniform noise between [-0.5,0.5] will be added.
* **--clearance-car**: clearance between other agents to be kept when spawning a vehicle.
* **--clearance-bike**: clearance between other agents to be kept when spawning a bike or motorcycle.
* **--clearance-pedestrian**: clearance between other agents to be kept when spawning a walker.
* **--collision**: enable or disable collision response for all traffic agents.

## Changing the Camera view

The camera view in SUMMIT can be either changed using mouse / keyboard, or through code.

### Mouse / keyboard

To change the camera angle, hold down the right mouse button and drag your mouse around; 
To change the camera position, hold down the right mouse button and use the WASD keys.

### Python API

Alternatively, you can use the following code to change the view point in the server.
```python
client = carla.Client(host, port)
client.get_world().get_spectator().set_transform(carla.Transform(                
        carla.Location((x, y, z),
        carla.Rotation(pitch, yaw, roll)))
```

### Camera actor
If you need to frequently change the view point of SUMMIT such as tracking an vehicle, we recommend to spawn a seperate camera actor and attach it to the tracked vehicle. An example script can be found in the [expert planner repo](https://github.com/AdaCompNUS/context-pomdp/blob/master/summit_connector/src/spectator.py).
