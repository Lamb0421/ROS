# 確認系統區域設置

### 查看系統區域是否為UTF-8
```
locale
```
### 如不是UTF-8，更改方式如下：
```
sudo apt update
sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
```
### 確認系統區域是否更改
```
locale
```
# 啟用Ubuntu Universe存儲庫
```
sudo apt install software-properties-common
sudo add-apt-repository universe
```
### 如果啟用失敗可先跳過

# 添加 ROS 2 GPG 密鑰
```
sudo apt update 
sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
# 存儲庫添加到列表中
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
# ROS-Base 安裝

### 由於 Ubuntu 22.04 的早期更新相關軟件包非常重要，請務必執行update、upgrade
```
sudo apt update
sudo apt upgrade
```
### 安裝base版本
```
sudo apt install ros-iron-ros-base
```
### 安裝Full版本
```
sudo apt install ros-iron-desktop
```
