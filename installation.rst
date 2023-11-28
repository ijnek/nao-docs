Installation
############

.. note::

    Instructions here assume that you are in a ROS2 workspace
    root directory.

Cloning repositories
********************

In your ROS2 workspace, clone the repository, and install dependencies:

.. tabs::

    .. group-tab:: Humble / Iron

        If using Humble or Iron, use the ``iron`` branch:

        .. code-block:: console

            git clone https://github.com/ijnek/nao.git -b iron src/nao
            rosdep install --from-paths src --ignore-src -y

    .. group-tab:: Rolling / J-turtle onwards

        Otherwise, use the default branch:

        .. code-block:: console

            git clone https://github.com/ijnek/nao.git src/nao
            rosdep install --from-paths src --ignore-src -y


Obtaining 3D model
******************

.. tabs::

    .. group-tab:: Humble / Iron

        Due to software licensing issues, the 3D models for the Nao cannot be included
        in this repository, so it must be manually installed. You will be prompted by the installer
        to accept the terms and conditions.

        Run the installer, and **leave the install directory as the default**:

        .. code-block:: console

            src/nao/nao_description/install.sh

    .. group-tab:: Rolling / J-turtle onwards

        For Rolling and J-turtle onwards, the `official meshes repository`_ from Aldebaran is used.
        This package is not available as a binary yet, and so you must clone the repository into your workspace.

        In your workspace directory, run

        .. code-block:: console

            git clone git@github.com:ros-naoqi/nao_meshes2.git src/nao_meshes2

Building
********

To build the package and its dependencies, in the workspace root directory, run:

.. code-block:: console

   colcon build

.. _official meshes repository: https://github.com/ros-naoqi/nao_meshes2
