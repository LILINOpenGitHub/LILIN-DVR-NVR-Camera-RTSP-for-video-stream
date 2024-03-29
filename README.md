# RTSP-stream-for-LILIN DVR NVR

Protocol Supported:
RTSP over TCP at 554 port

# Product Supported:
NVR116, NVR109, NVR104, NVR404, NVR408m, NVR100, NVR200, NVR400, NVR1400, NVR2400, NVR5416, NVR5104E, NVR5208E, NVR5416E, NVR5832, NVR5832S, NVR3816, NVR3416, NVR3216

DHD5104, DHD5108, DHD5216

# Firmware Requirement:
NVR/DVR Firmware 1.1.58 and later (SVN#7189) can support RTSP stream for NVR/DVR

# 1.0  NVR H.264 RTSP Video & Audio Streaming

To test NVR H.264 streams via RTP/RTSP/HTTP, you can verify the streams by using QuickTime or VLC.  The stream contains both video and audio if the IP camera contains audio signal.

# 2.0  NVR H.264 RTSP Live Syntax

**Syntax:**
rtsp://(username):(password)@(IP address):(port)/rtspstream?channel=(ch)&stream=(stream)

**Example:** <BR>
Playback recording for channel #2’s primary (SD) stream:

rtsp://admin:1111@192.168.3.243:554/rtspstream?channel=1&stream=1

**Example:** <BR>
Playback recording for channel #2’s secondary (HD) stream:

rtsp://admin:1111@192.168.3.243:554/rtspstream?channel=1&stream=1

**Parameters:** <BR>
| Token | Type | Comments |
| ------|------- | ---- |
| username | String	 | User name of the NVR  |
| password | String | 	Password of the NVR  |
| IP address | String	 | IP address of the NVR  |
| port  | Number	 |  Port number of the NVR |
| ch | Number	 | Channel # 0~31 of the NVR/DVR |
| stream | Number  | 1: primary stream (SD), 2: secondary stream (HD)  |

# 2.1  NVR H.264 RTSP Playback Syntax
 
**Syntax:** <BR>

rtsp://(user):(password)@(IP address):(port)/rtspstream?channel=(ch)&stream=(stream)&playback=(date)

 **Example:**
 rtsp://admin:1111@192.168.0.111:554/rtspstream?channel=0&stream=0&playback=2021/08/12/22/35/00
 
**Parameters:** <BR>
| Token | Type | Comments |
| ------|------- | ---- |
| username | String	 | User name of the NVR  |
| password | String | 	Password of the NVR  |
| IP address | String	 | IP address of the NVR  |
| port  | Number	 |  Port number of the NVR |
| ch | Number	 | Channel # 0~31 of the NVR/DVR |
| date | 	String	 | YYYYMMDD-hhmmss |
| YYYY | Number | year, e.g. 2015 |
| MM | Number |  month |
| DD | Number |  day |
| hh | Number |  hour |
| mm | Number | |minute |
| ss | Number | second   |
| stream | Number  | 1: primary stream (SD), 2: secondary stream (HD)  |
 
# 2.2  Playback Commands
Only RTSP Play and Pause are supported.
 
# 3.0  RTSP Streaming via VLC
Click on Media->Open Network Stream.  Enter the RTSP URL at Network Protocol box and click Play button.
![image](https://github.com/LILINOpenGitHub/LILIN-DVR-NVR-RTSP-for-video-stream/blob/main/images/vlc.png)
<BR>
# 4.0  RTSP Streaming via FFPlay
TCP
ffplay -rtsp_transport tcp "rtsp://admin:Pass1234@36.226.49.159:554/rtspstream?channel=0&stream=1"

UDP
ffplay "rtsp://admin:Pass1234@36.226.49.159:554/rtspstream?channel=0&stream=1"
 
# 5.0 C# sample code 
Visit the C# sample code [here](https://github.com/LILINOpenGitHub/Python-CSharp--Code-of-RTSP-MJPG-Video-with-AI-Bounding-Box-Display-for-LILIN-Yolo-Camera-/tree/main/C%23)
 
![image](https://github.com/LILINOpenGitHub/Python-CSharp--Code-of-RTSP-MJPG-Video-with-AI-Bounding-Box-Display-for-LILIN-Yolo-Camera-/blob/main/image/nvrrtsp.gif)


