

# Preparation : 
Make sure your Ubuntu software and update settings are as follows : 
- Select all sources available
- Download From : main server not regional

![](https://i.imgur.com/g138qtU.png)



# Set locale
Make sure you have a local that supports UTF-8
using this script: 

```
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```
# Setup Sources 
- Add the ROS 2 apt repository to your system.



```
sudo apt install software-properties-common
sudo add-apt-repository universe
```
```
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
# Install ROS Packages 
```
sudo apt update
```
```
sudo apt upgrade
```
```
sudo apt install ros-humble-desktop
```
```
sudo apt install ros-humble-ros-base
```
```
sudo apt install ros-dev-tools
```
# Installing Gazebo , Turtlesim and rqt 
- Gazebo :
Gazebo brings a fresh approach to simulation with a complete toolbox of development libraries and cloud services to make simulation easy.

We only have to change "ROS_DISTRO" with distrubition name in our case humble :
```
sudo apt-get install ros-ROS_DISTRO-ros-gz
sudo apt-get install ros-humble-ros-gz
```
- Turtlesim :
Turtlesim is a lightweight simulator for learning ROS 2. It illustrates what ROS 2 does at the most basic level to give you an idea of what you will do with a real robot or a robot simulation later on.
```
sudo apt update

sudo apt install ros-humble-turtlesim
```
- rqt

rqt is a software framework of ROS that implements the various GUI tools in the form of plugins.
```
sudo apt update

sudo apt install '~nros-humble-rqt*'
```