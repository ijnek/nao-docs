Installation
############

.. note::

    Instructions here assume that you are in a ROS2 workspace
    root directory.

Cloning repositories
********************

In your ROS2 workspace, clone the repository:

.. code-block:: console

   git clone https://github.com/ijnek/nao.git src/nao
   vcs import src < src/nao/dependencies.repos

Install 3D model
*****************

Due to software licensing issues, the 3D models for the Nao cannot be included
in this repository, so it must be manually installed using the following instructions:

.. code-block:: console

    cd src/nao/nao_description && mkdir tmp && cd tmp
    wget https://github.com/ros-naoqi/nao_meshes_installer/raw/master/naomeshes-0.6.7-linux-x64-installer.run
    chmod +x naomeshes-0.6.7-linux-x64-installer.run && ./naomeshes-0.6.7-linux-x64-installer.run  --prefix .
    mv -t ../  meshes/ texture/
    cd ../ && rm -rf tmp/ && cd ../../../

.. warning::

    Don't change the install directory in the installer

Building
********

To build the package and its dependencies, in the workspace root directory, run:

.. code-block:: console

   colcon build