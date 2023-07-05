# android-sdk-platform-tools-supporter

```
import sys
sys.path.append("/opt")
import common

https://www.bangseongbeom.com/sys-path-pythonpath.html
```

```
import os
import time
from python_supporter.change_ip import ChangeIp

base_directory = os.path.dirname(__file__) + "/platform-tools"
change_ip = ChangeIp(base_directory)

device = change_ip.connect_to_device()
    
if not device:
    print(f"USB에 디바이스가 연결되지 않았습니다.")
    exit()

print(f"연결된 디바이스: {device}")

print("모바일 데이터 해제")
change_ip.data_disable()

print("1초 쉬기")
time.sleep(1)

print("모바일 데이터 연결")
change_ip.data_enable()

ip = change_ip.check_ip()
print(f"PC IP: {ip}")
```
