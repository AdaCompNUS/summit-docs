<h1>Changing Viewpoint</h1>

he view point in SUMMIT can be either changed using mouse / keyboard, or through code.

# Mouse / keyboard

To change the camera angle, hold down the right mouse button and drag your mouse around. 

To change the camera position, hold down the right mouse button and use the WASD keys.

# Python API
Alternatively, you can use the following code to change the view point in the server.
```python
client = carla.Client(host, port)
client.get_world().get_spectator().set_transform(carla.Transform(                
        carla.Location((x, y, z),
        carla.Rotation(pitch, yaw, roll)))
```

# Camera actor
If you need to frequently change the view point of SUMMIT such as tracking an vehicle, we recommend to spawn a seperate camera actor and attach it to the tracked vehicle. An example script can be found in the [expert planner repo](https://github.com/AdaCompNUS/context-pomdp/blob/master/summit_connector/src/spectator.py).