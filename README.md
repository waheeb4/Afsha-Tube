# 🎬Afsha Tube – LAN Video Streamer
Welcome to Afsha Tube, a lightweight YouTube-style app that allows you to stream videos within your local network. Users can connect to your host machine via its IP address and stream videos directly from your system — without downloading anything.

⚠️ This project is for LAN use only — it's not designed for internet-scale streaming.

# 📦 Features
- 🎥 Stream videos from the host machine in real-time

- 🔊 Synchronized audio and video playback

- 🖼️ Video thumbnails with durations

- 🖱️ Click-to-play UI with pause/resume controls

- 🧠 Efficient resource handling with threading

- 🔒 Zero download – all data is streamed

# 🧰 Tech Stack
- Frontend GUI: customtkinter

- Video Processing: OpenCV, PIL

- Audio Handling: PyAudio, FFmpeg (via subprocess)

- Streaming Protocol: Custom TCP protocol using socket

- Threading & Concurrency: Python threading, ThreadPoolExecutor

# 🖥️ How It Works
# Server (host machine)
- Listens for video and audio connections on ports 9999 and 10000.

- Sends a video list with thumbnails and durations.

- Streams video and audio data to connected clients.

- Uses FFmpeg to handle audio decoding and OpenCV for video.

# Client (viewer)
- Connects to the host using its IP.

- Displays available videos with thumbnails.

- Streams selected video and audio for playback.

- Supports pause/resume and back-to-menu.

# 🧪 Setup Instructions
## 🔧 Prerequisites

Install required packages on both server and client:
customtkinter pillow opencv-python numpy pyaudio ffmpeg

## 🚀 Running the Server
    - python server.v3.0.py
It will display the host's IP address — share this with clients on the same network.

    - python gui.v1.0.py
Enter the server's IP and connect.

Browse and double-click a video to start streaming.

# 🌐 Network Architecture
[Client] ─────► [Server (Video Port 9999)] 
         ─────► [Server (Audio Port 10000)]

All communication happens over TCP sockets.

Video/audio data is streamed using a custom protocol:

Each packet contains:

- 8-byte size header

- 5-byte type label ("VIDEO"/"AUDIO") payload

🎞️ Videos must be .mp4 and exist in the predefined server directory
