Nao State Publisher
*******************

Inherits `robot_state_publisher`_ , but rather than listening for topic:

* **joint_states** (`sensor_msgs/JointState`_)

it listens for topic:

* **sensors/joint_positions** (`nao_sensor_msgs/msg/JointPositions`_)

and publishes ROS2 transforms. 

See `robot_state_publisher`_'s documentation for more details.


.. _robot_state_publisher: http://wiki.ros.org/robot_state_publisher
.. _sensor_msgs/JointState: http://docs.ros.org/en/melodic/api/sensor_msgs/html/msg/JointState.html
.. _nao_sensor_msgs/msg/JointPositions: https://nao-interfaces-docs.readthedocs.io/en/latest/sensor-msgs.html#jointpositions