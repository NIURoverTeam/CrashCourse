# Turtlesim Redux: Websocket edition

After you have sourced the environment that has the things you need, you can start rosbridge.

Do note that overlapping ports can cause issues.  Pick a port that is not in use.
```bash
ros2 run rosbridge_server rosbridge_websocket.py --port 8081
```
