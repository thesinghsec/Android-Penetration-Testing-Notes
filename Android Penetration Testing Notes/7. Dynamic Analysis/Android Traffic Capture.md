### 1. Tools

* [**TCPDump:**](https://androidfilehost.com/?fid=1395089523397939647)
* **Netcat:** (already installed in emulator)
* **Wireshark**

### 2. Push TCPDump Binary to Emulator

```
adb push tcpdump /tmp/
```
![image](https://github.com/user-attachments/assets/56ee61a3-66c1-463a-a63a-52042a2821dc)


### 3. Open ADB Shell

Move to `tmp` directory and provide TCPDump executable privileges.
![image](https://github.com/user-attachments/assets/d98c5473-d6fd-4558-a451-7df1d1bbc2d4)


### 4. Capture Traffic

```
./tmp/tcpdump -w - | nc -l -p 31337
```
![image](https://github.com/user-attachments/assets/c07776c1-5ed5-4b15-ab1d-175fb1e2e277)


### 5. Port Forwarding

From a new tab, run:

```
adb forward tcp:12345 tcp:31337
```
![image](https://github.com/user-attachments/assets/59a18b9d-737d-46cb-9c95-083aa6c98f5a)


### 6. Play with the Application

Interact with the application while Netcat captures the traffic. After done, hit `Ctrl+C`.

### 7. Analyze in Wireshark

Do a quick `ls` — you should have `newresulst.pcap`.
Open this file with Wireshark to view the captured device traffic.
![image](https://github.com/user-attachments/assets/85ca0b6d-95ac-4dc9-85d5-3885ad51439f)

