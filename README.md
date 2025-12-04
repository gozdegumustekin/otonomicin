#tam çalışan, ROS2 workspace içinde kullanabileceğin bir run_demo.sh dosyası:

***Terminalde:***

cd ~/ros2_ws
nano run_demo.sh

*********Açılan kısıma direkt yapıştır:******

#!/bin/bash

# ROS2 environment
source /opt/ros/humble/setup.bash
source ~/ros2_ws/install/setup.bash

echo "🚀 TTFEST TAM DEMO BAŞLIYOR"

# 1) Gazebo Simülasyonu
echo "📦 Gazebo simülasyonu açılıyor..."
gnome-terminal -- bash -c "source /opt/ros/humble/setup.bash; source ~/ros2_ws/install/setup.bash; ros2 launch ttfest_pkg ttfest_launch.py; exec bash"

# 5 saniye beklemesi iyi olur (simülasyon yükleniyor)
sleep 5

# 2) Kamera Node
echo "📷 Kamera node başlatılıyor..."
gnome-terminal -- bash -c "source /opt/ros/humble/setup.bash; source ~/ros2_ws/install/setup.bash; ros2 run ttfest_pkg camera_node.py; exec bash"

# 3) Kontrol Node
echo "🎮 Kontrol node başlatılıyor..."
gnome-terminal -- bash -c "source /opt/ros/humble/setup.bash; source ~/ros2_ws/install/setup.bash; ros2 run ttfest_pkg control_node.py; exec bash"

# 4) LIDAR Node
echo "📡 LIDAR node başlatılıyor..."
gnome-terminal -- bash -c "source /opt/ros/humble/setup.bash; source ~/ros2_ws/install/setup.bash; ros2 run ttfest_pkg lidar_node.py; exec bash"

# 5) Şerit Takibi Node
echo "🚗 Şerit Takibi başlatılıyor..."
gnome-terminal -- bash -c "source /opt/ros/humble/setup.bash; source ~/ros2_ws/install/setup.bash; ros2 run ttfest_pkg lane_following_node.py; exec bash"

echo "✨ Tüm nodelar açıldı. Demo hazır!"


****yapıştırdıktan sonra******

Kaydet → CTRL + O
Çık → CTRL + X




***********Scripte çalışma izni ver: (terminale)*********

chmod +x run_demo.sh




************Başlatmak için:**********

./run_demo.sh





