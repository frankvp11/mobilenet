sudo docker run -it --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --network host nvcr.io/nvidia/l4t-tensorflow:r32.7.1-tf2.7-py3
python3 -m pip install --upgrade pip
python3 -m pip install opencv-python==4.5.3.56

import os
import time
time.sleep(15)
os.system("sudo docker run -it --rm -e DISPLAY=$DISPLAY --device /dev/video0:/dev/video0 -v /tmp/argus_socket:/tmp/argus_socket -v /tmp/.X11-unix:/tmp/.X11-unix --network host nvcr.io/nvidia/l4t-tensorflow:r32.7.1-tf2.7-py3")
