# ubuntu_setup

For git install the following:
```
sudo apt install git
```
Install pycharm. For community:
```
sudo snap install pycharm-community --classic
```
for pro:
```
sudo snap install pycharm-professional --classic
```

You'll also need these for python venv and development:
```
sudo apt install python3-distutils python3-dev python3-setuptools python3-pip python3-venv libssl-dev libffi-dev build-essential 
```

And screen, tmux or byuobi:
```
sudo apt install byobu screen
```

## install zsh/ohmyzsh:
```
sudo apt install zsh
```
ohmyzsh
```
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
### Agnoster theme (optional)
```
sudo apt-get install fonts-powerline
cd ~
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="agnoster"/g' .zshrc
```

## Putting it all together:
Version 1
```
sudo apt update
sudo apt install git python3-distutils python3-dev python3-setuptools python3-pip python3-venv libssl-dev libffi-dev zsh fonts-powerline vim build-essential byobu screen
sudo snap install pycharm-professional --classic
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
cd ~
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="agnoster"/g' .zshrc
```
Version 2
```
sudo apt update
sudo apt install git python3-distutils python3-dev python3-setuptools python3-pip libssl-dev libffi-dev zsh openssh-server vim build-essential byobu screen
sudo snap install pycharm-community --classic
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Install python 3.9
```
sudo apt update 
sudo apt install software-properties-common 
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.9-full python3.9-dev
```

## Install cuda
Check out instructions [here](https://developer.nvidia.com/cuda-downloads)

For Ubuntu 18.04 on x86_64:
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-ubuntu1804.pin
sudo mv cuda-ubuntu1804.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1804-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-1-local-10.1.243-418.87.00/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```

For Ubuntu 16.04 on x86_64:
```
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-ubuntu1604.pin
sudo mv cuda-ubuntu1604.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget http://developer.download.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda-repo-ubuntu1604-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604-10-1-local-10.1.243-418.87.00_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-1-local-10.1.243-418.87.00/7fa2af80.pub
sudo apt-get update
sudo apt-get -y install cuda
```
# Troubleshooting
If the ethernet adapter doesn't work for some reason do the following: attach an old usb ethernet/wifi adapter, update the software.
Next, run the following commands:
```
sudo apt install linux-firmware linux-generic-hwe-18.04
```
