Nao State Publisher (Deprecated)
################################

.. warning::

  Nao State Publisher is deprecated in ROS 2 J-turtle and will be removed in ROS 2 K-turtle.
  Please :ref:`use robot state publisher directly<rsp_example>` instead.

The Nao State Publisher inherits from, and achieves the same purpose as a `robot_state_publisher`_,
to publish ROS transforms.

Running the nao_state_publisher
*******************************

Start the nao_state_publisher:

.. code-block:: console

   ros2 launch nao_state_publisher nao_state_publisher_launch.py

Why not use `robot_state_publisher`_?
*************************************

The nao_state_publisher listens to msgs specific to the NAO robot, which cannot be achieved
with the robot_state_publisher.

Specifically, rather than subscribing to

* **joint_states** (`sensor_msgs/JointState`_) - which robot_state_publisher does

the nao_state_publisher subscribes to nao-specific joint positions

* **sensors/joint_positions** (`nao_sensor_msgs/msg/JointPositions`_) up until ROS 2 Iron
* **sensors/joint_positions** (`nao_lola_sensor_msgs/msg/JointPositions`_) for later ROS 2 distros

.. seealso::

  `robot_state_publisher`_'s documentation for more details.


.. _robot_state_publisher: http://wiki.ros.org/robot_state_publisher
.. _sensor_msgs/JointState: http://docs.ros.org/en/melodic/api/sensor_msgs/html/msg/JointState.html
.. _nao_sensor_msgs/msg/JointPositions: https://nao-interfaces-docs.readthedocs.io/en/latest/sensor-msgs.html#jointpositions
.. _nao_lola_sensor_msgs/msg/JointPositions: https://nao-lola.readthedocs.io/en/latest/sensor-msgs.html#jointpositions
