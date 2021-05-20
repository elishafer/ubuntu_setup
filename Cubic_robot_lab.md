# Create thing for cubic

What do we need? We want to create an iso for the setup of the robot

## Cubic (Custom Ubuntu ISO Creator)

This program takes an existing ISO and lets you customise it through a terminal.

```
sudo apt update
sudo apt install git python3-distutils python3-dev python3-setuptools python3-pip python3-venv libssl-dev libffi-dev zsh fonts-powerline vim build-essential
sudo snap install pycharm-professional --classic
```

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt update
sudo apt install ros-melodic-desktop-full
```

### Additional ROS stuff

```
apt-get install python-rosdep ros-melodic-panda-moveit-config python-catkin-tools ros-melodic-moveit
apt install ros-melodic-robot-controllers ros-melodic-position-controllers
apt install ros-melodic-ros-control ros-melodic-ros-controllers
apt install ros-melodic-rospy-message-converter
apt install python-numba
```

### Franka Emika Panda
```
apt install ros-melodic-libfranka ros-melodic-franka-ros
```
#### RT Kernel Install - Doesn't work. Install after installing Ubuntu
```
apt-get install build-essential bc curl ca-certificates fakeroot gnupg2 libssl-dev lsb-release libelf-dev bison flex
```

Install the RT kernel
```
curl -SLO https://www.kernel.org/pub/linux/kernel/v5.x/linux-5.4.3.tar.xz
curl -SLO https://www.kernel.org/pub/linux/kernel/v5.x/linux-5.4.3.tar.sign
curl -SLO https://mirrors.edge.kernel.org/pub/linux/kernel/projects/rt/5.4/older/patch-5.4.3-rt1.patch.xz
curl -SLO https://mirrors.edge.kernel.org/pub/linux/kernel/projects/rt/5.4/older/patch-5.4.3-rt1.patch.sign
```

```
xz -d linux-5.4.3.tar.xz
xz -d patch-5.4.3-rt1.patch.xz
```
```
gpg2 --verify linux-5.4.3.tar.sign
```

```
tar xf linux-5.4.3.tar
cd linux-5.4.3
patch -p1 < ../patch-5.4.3-rt1.patch
```

### RealSense
```
apt-get install ros-melodic-realsense2-camera
```

```
sudo apt-key adv --keyserver keys.gnupg.net --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE
```
```
