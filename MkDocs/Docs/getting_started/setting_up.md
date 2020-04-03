<h1>Setting up SUMMIT</h1>

## Requirements
The requirements from SUMMIT derive from those of CARLA. Please ensure that you have met the [requirements of CARLA](https://carla.readthedocs.io/en/latest/start_quickstart/#requirements) in order to use SUMMIT. 

!!! important
    (As an exception, **SUMMIT only supports Linux**, and we do not have any foreseeable plans to extend support for Windows or macOS)

In addition, we make use of a few additional packages, as listed below.
  
  * Python 2 packages: `pip2 install --user pathlib2 Pyro4`
  * Python 3 packages: `pip3 install --user pathlib Pyro4`
  * (Optional) [JOSM](https://josm.openstreetmap.de/): A set of tools to edit to downloaded OSM files. Highly recommended if you intend to use your own maps. If so, we recommend that you familiarize yourself with JOSM's usage.
  * (Optional) [SUMO tools](https://sumo.dlr.de/docs/Downloads.php): A set of tools to convert OSM files into SUMO networks, and to edit SUMO networks. Highly recommended if you intend to use your own maps. If so, we also recommend that you familiarize yourself with the usage of SUMO's tools, in particular [NETCONVERT](https://sumo.dlr.de/docs/NETCONVERT.html) and [NETEDIT](https://sumo.dlr.de/docs/NETEDIT.html).

## Downloading SUMMIT

Download the latest SUMMIT package from the [downloads page](../../references/releases), and extract the contents somewhere of your preference.
