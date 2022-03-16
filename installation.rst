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

.. warning::

    Don't change the install directory in the installer

Due to software licensing issues, the 3D models for the Nao cannot be included
in this repository, so it must be manually installed. You will be prompted by the installer
to accept the terms and conditions.

Run the following:

.. code-block:: console

    
    src/nao/nao_description/install.sh


Building
********

To build the package and its dependencies, in the workspace root directory, run:

.. code-block:: console

   colcon build
