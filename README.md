## OctoPi WebRTC PoC

Based on https://github.com/johnboiles/aiortc

## Setup

```
ssh pi@octopi.local
git clone https://github.com/crysxd/octopi-webrtc-streamer
cd octopi-webrtc-streamer
git submodule init
git submodule update
python3 -m venv venv
source venv/bin/activate
sudo apt-get install libopus-dev libvpx-dev
pip install --upgrade pip
pip install aiohttp Pillow
pip install -e ./aiortc/
```

Run `sudo nano /boot/config.txt`, set `gpu_mem=256` and restart

## Run

```
ssh pi@octopi.local
sudo systemctl stop webcamd
sudo systemctl stop ffmpeg_hls
cd octopi-webrtc-streamer
source venv/bin/activate
python webcam.py --resolution 1280x720 --preferred-codec video/H264
```

Open http://octopi.local:8080

## OctoPrint setup:

- Webcam URL: webrtc://octopi.local:8080/webrtc
- Snapshot URL: http://octopi.local:8080/jpeg
