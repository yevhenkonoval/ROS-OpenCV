# Проект: Автономний автомобіль

![Відео проекту](res/comp_vision.gif)

## Дерево проекту

```
self_driving_car_pkg/
├── launch/
│ ├── world_gazebo.launch.py
├── worlds/
│ ├── sdc.world
├── Detection/
│ ├── Signs/
│ ├── TrafficLights/
│ ├── Lanes/
│ └── HaarCascade/
├── GPS_Navigation/
│ ├── bot_mapping.py
├── setup.py
├── package.xml
└── resource/
```

## Як встановити ROS Foxy

1. Відкрийте термінал.
2. Додайте репозиторій ROS 2 до вашої системи:

```bash
sudo apt update && sudo apt install -y software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:ros/ppa
```

3. Встановіть ROS 2 Foxy:

```bash
sudo apt update
sudo apt install -y ros-foxy-desktop
```

4. Встановлення необхідних бібліотек

```bash
sudo apt install -y python3-colcon-common-extensions
sudo apt install -y ros-foxy-gazebo-msgs
sudo apt install -y ros-foxy-gazebo-plugins
sudo apt install -y ros-foxy-gazebo-ros-pkgs
```

5. Налаштуйте середовище:

```bash
echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

6. Додати моделі до Gazebo (попередньо створивши папку)

```bash
mkdir -p ~/.gazebo/models
```

## Створення Python virtualenv

1. Завантаження

```bash
python3 -m pip install --user virtualenv
```

2. Створення віртуального середовища

```bash
python3 -m virtualenv myvenv
```

3. Запуск віртуального середовища

```bash
source myvenv/bin/activate
```

4. Завантаження необхідних бібліотек

```bash
pip3 install -r python_requirements.txt
```

## Компіляція проекту

```bash
touch ROS2SDC_VENV/COLCON_IGNORE
colcon build
```

## Як запустити проект

### Запуск середовища

![Запуск Gazebo](res/gazebo_launch.gif)

1. Перейдіть до каталогу проекту:

```bash
cd path/to/ROS-OpenCV
```

2. Активуйте віртуальне середовище Python

```bash
source ROS2SDC_VENV/bin/activate
```

3. Додайте необхідні залежності

```bash
source install/setup.bash
```

4. Запустіть проект за допомогою команди:

```bash
ros2 launch self_driving_car_pkg world_gazebo.launch.py
```

### Запуск моделі навігації

![Запуск навігації](res/comp_vision.gif)

1. Перейдіть до каталогу проекту:

```bash
cd path/to/ROS-OpenCV
```

2. Активуйте віртуальне середовище Python

```bash
source ROS2SDC_VENV/bin/activate
```

3. Додайте необхідні залежності

```bash
source install/setup.bash
```

4. Запустіть модель за допомогою команди:

```bash
ros2 run self_driving_car_pkg computer_vision_node
```
