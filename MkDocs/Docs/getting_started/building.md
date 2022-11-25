<h1>Building SUMMIT</h1>

!!! important
    Building SUMMIT is only necessary if you wish to edit SUMMIT. If you only wish to use the simulator, the [setup steps](../setting_up) are sufficient.

<h2>Ubuntu 20.04 Instructions</h2>

<h4>1. Setup dependencies</h4>
```bash
sudo apt-add-repository "deb http://apt.llvm.org/focal/ llvm-toolchain-focal main"
sudo apt install build-essential clang-10 lld-10 g++-7 cmake ninja-build libvulkan1 python3-dev python3-pip python-is-python3 libpng-dev libtiff5-dev libjpeg-dev tzdata sed curl unzip autoconf libtool rsync libxml2-dev git libboost1.71-dev-all ccache
sudo update-alternatives --install /usr/bin/clang++ clang++ /usr/lib/llvm-10/bin/clang++ 180
sudo update-alternatives --install /usr/bin/clang clang /usr/lib/llvm-10/bin/clang 180
pip3 install --user setuptools
```

Please ensure that the above steps successfully installs <b>Clang 10.0</b>, <b>Boost 1.71</b>, and <b>Python 3.8</b> on your system. These specific versions are necessary for compilation to work properly. If compilation does not work, ensure that no other versions of these programs/libraries exist on your system.

<h4>2. Setup and compile Unreal Engine</h4>
You need to [link your Github account with Unreal](https://www.epicgames.com/help/en-US/epic-accounts-c5719348850459/connect-accounts-c5719351300507/how-do-i-link-my-unreal-engine-account-with-my-github-account-a5720369784347?sessionInvalidated=true) before you can run the following to clone the repository.
```bash
git clone --depth 1 -b 4.26 https://github.com/CarlaUnreal/UnrealEngine.git ~/UnrealEngine_4.26
cd ~/UnrealEngine_4.26
./Setup.sh && ./GenerateProjectFiles.sh && make
```
<h4>3. Setup and compile SUMMIT</h4>
```bash
git clone https://github.com/AdaCompNUS/summit
cd ~/summit
./Update.sh

# This specific asset is known to be broken in CARLA's assets repository, so we remove it.
Unreal/CarlaUE4/Content/Carla/Static/Vegetation/Veg_Tree_DatePalm_v001.uasset

# Patch default map and add assets for dynamic meshes.
cp CustomAssets/EmptyMap.umap Unreal/CarlaUE4/Content/Carla/Maps/TestMaps/EmptyMap.umap
cp CustomAssets/EmptyMap_BuiltData.umap Unreal/CarlaUE4/Content/Carla/Maps/TestMaps/EmptyMap_BuiltData.umap
cp CustomAssets/M_Tile.uasset Unreal/CarlaUE4/Content/Carla/Static/GenericMaterials/Ground/M_Tile.uasset

# Build what you need.
make LibCarla # To build LibCarla only.
make PythonAPI # To build PythonAPI only.
make launch # To build UE editor with SUMMIT plugins.
make package # To build SUMMIT package for distribution.
```

<h2>Ubuntu 18.04 Instructions</h2>

The build instructions for SUMMIT are exactly the same as those in CARLA.

To build SUMMIT, follow exactly the [build instructions for CARLA](https://carla.readthedocs.io/en/latest/how_to_build_on_linux/), with some additional steps:

  * Clone and use the [SUMMIT repository](https://github.com/AdaCompNUS/summit) instead of the CARLA repository.
  * **Before building SUMMIT**, install [ccache](https://ccache.dev/): `sudo apt install ccache`.
  * **After getting assets**, copy the following SUMMIT specific assets into the assets folder, overriding any existing files:
    * Copy `<summit_root>/CustomAssets/EmptyMap.umap` to `<summit_root>/Unreal/CarlaUE4/Content/Carla/Maps/TestMaps/EmptyMap.umap`
    * Copy `<summit_root>/CustomAssets/EmptyMap_BuiltData.umap` to `<summit_root>/Unreal/CarlaUE4/Content/Carla/Maps/TestMaps/EmptyMap_BuiltData.umap`
    * Copy `<summit_root>/CustomAssets/M_Tile.uasset` to `<summit_root>/Unreal/CarlaUE4/Content/Carla/Static/GenericMaterials/Ground/M_Tile.uasset`


