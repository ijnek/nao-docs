Usage
#####

The nao.urdf file is the URDF model of the NAO robot.
It is available in the nao_description package's share directory.

.. _rsp_example:

Running Robot State Publisher
*****************************

To run robot_state_publisher from a python3 launch file, do the following:

.. code-block:: python3

    import os
    from ament_index_python.packages import get_package_share_directory
    from launch import LaunchDescription
    from launch_ros.actions import Node

    def generate_launch_description():

        urdf_file_name = 'nao.urdf'
        urdf = os.path.join(get_package_share_directory('nao_description'), 'urdf', urdf_file_name)
        with open(urdf, 'r') as infp:
            robot_desc = infp.read()

        return LaunchDescription([
            Node(
                package='robot_state_publisher',
                executable='robot_state_publisher',
                name='robot_state_publisher',
                output='screen',
                parameters=[{'robot_description': robot_desc}],
                arguments=[urdf])
        ])
