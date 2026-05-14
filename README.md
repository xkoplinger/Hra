Na stiahnute by malo stačiť toto
cd ~/ros2_ws/src,
git clone https://github.com/xkoplinger/Hra.git vacuum_game

Malo by sa to po staihnutí premenovať ako vacuum_game

Potom:
cd ~/ros2_ws,
colcon build --packages-select vacuum_game,
source install/setup.bash

A cez jednotlive terminály to spustiť takto:

1. ros2 run vacuum_game vacuum_node --ros-args -p game_mode:=pvp
2. rviz2
3. ros2 run teleop_twist_keyboard teleop_twist_keyboard
4. ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r cmd_vel:=/robot2/cmd_vel  Toto zapnúť len ak je pvp, na ovládanie druhého robota
5. ros2 service call /reset_game std_srvs/srv/Empty  Reset hry

Takto by to malo fungovať, v tom media su aj tie videa kde som to mal nahráte ako to ukazujem. A potom Nastavenia tam som nahral všetko ako som mal spravené v rviz
