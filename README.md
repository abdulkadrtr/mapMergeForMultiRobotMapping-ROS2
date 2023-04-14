# mapMergeForMultiRobotMapping-ROS2
This ROS2 node subscribes to two different map messages, merges them, and 
publishes the merged map to the /merge_map topic.

## How does it work

The Merge Map ROS2 package is designed to merge map messages from `/map1` and `/map2` topics, and publish the merged map to the `/merge_map` topic. To use this package, follow the instructions below:

1. Copy the `merge_map` folder to the `src` directory of your ROS2 workspace.
2. Run the following command: `ros2 launch merge_map merge_map_launch.py`. This command starts the map merging node and opens an RViz2 window.
3. In the RViz2 window, you can observe the merged map. Whenever one of the maps being merged is updated, the `merge_map` node will also update the merged map accordingly.

Make sure to have ROS2 installed and properly configured in your environment before using this package. For more information, please refer to the ROS2 documentation.


## launch.py customization

The Merge Map ROS2 package can be customized and launched in your own `launch.py` file by adding the following code block. You can update `/yourMapName1` and `/yourMapName2` topics according to your project:

```
Node(
    package='merge_map',
    executable='merge_map',
    output='screen',
    parameters=[{'use_sim_time': True}],
    remappings=[
        ("/map1", "/yourMapName1"),
        ("/map2", "/yourMapName2"),
    ],
),
```

## Example

<img src="https://user-images.githubusercontent.com/87595266/231796297-5d719479-8866-40ee-b349-de3f9c70a976.png" width="950">

