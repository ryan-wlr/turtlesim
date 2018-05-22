// This program subscribes to turtle1/pose and shows its
// message on the screen.
#include <ros/ros.h>
#include <turtlesim/Pose.h>
#include <iomanip> // for std::setprecision and std::fixed

// A callback function. Executed each time a new pose
// message arrives.
void poseMessageReceived(const turtlesim::Pose& msg) {
  ROS_INFO_STREAM(std::setprecision(2) << std::fixed
    << "position=(" << msg.x << "," << msg.y << ")"
    << " direction=" << msg.theta);
}

int main(int argc, char **argv) {
  // Initialize the ROS  system and become a node.
  ros::init(argc, argv, "subscribe_to_pose");
  ros::NodeHandle nh;

  // Create a subscriber object. Topic, queue_size, pointer_to_callback_fuction. 
  ros::Subscriber sub = nh.subscribe("turtle1/pose", 1000, &poseMessageReceived);


  // Let ROS take over. Alternate to ros::sinOnce(). This asks ROS to execute all of the pendign callbacks form all the node's subs. 
  ros::spin();
}
