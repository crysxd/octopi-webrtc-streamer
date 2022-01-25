## OctoPi WebRTC PoC

Based on https://github.com/johnboiles/aiortc

## Setup

```
ssh pi@octopi.local
git clone https://github.com/crysxd/octopi-webrtc-streamer
cd octopi-webrtc-streamer
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install aiohttp aiortc Pillow
```

## Run

```
ssh pi@octopi.local
sudo systemctl stop webcamd
sudo systemctl stop ffmpeg_hls
cd octopi-webrtc-streamer
source venv/bin/activate
python webcam.py
```

Open http://octopi.local:8080

## OctoPrint setup:

- Webcam URL: webrtc://octopi.local:8080/webrtc
- Snapshot URL: http://octopi.local:8080/jpeg
