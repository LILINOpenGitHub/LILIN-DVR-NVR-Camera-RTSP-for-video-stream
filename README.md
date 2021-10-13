# RTSP-stream-for-LILIN DVR NVR

Protocol Supported:
RTSP over TCP at 554 port

# Product Supported:
NVR116, NVR109, NVR104, NVR404, NVR408m, NVR100, NVR200, NVR400, NVR1400, NVR2400, NVR5416, NVR5104E, NVR5208E, NVR5416E, NVR5832, NVR5832S, NVR3816, NVR3416, NVR3216

DHD5104, DHD5108, DHD5216

# Firmware Requirement:
NVR Firmware 1.1.58 and later can support RTSP stream for NVR

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
| ch | Number	 | Channel # 0~15 of the NVR |
| stream | Number  | 1: primary stream (SD), 2: secondary stream (HD)  |

# 2.1  NVR H.264 RTSP Playback Syntax
 
**Syntax:** <BR>

rtsp://(user):(password)@(IP address):(port)/rtspstream?channel=(ch)&stream=(stream)&playback=<date>

**Parameters:** <BR>
| Token | Type | Comments |
| ------|------- | ---- |
| date | 	String	 | YYYYMMDD-hhmmss |
| YYYY |  |year, e.g. 2015 |
| MM |  month |
| DD |  date |
| hh |  hour |
| mm | |minute |
| ss | second   |
| stream | Number  | 1: primary stream (SD), 2: secondary stream (HD)  |
 
# 3.0  RTSP Streaming via VLC
Click on Media->Open Network Stream.  Enter the RTSP URL at Network Protocol box and click Play button.

# 4.0  RTSP Streaming via FFPlay
TCP
ffplay -rtsp_transport tcp "rtsp://admin:Pass1234@36.226.49.159:554/rtspstream?channel=0&stream=1"

UDP
ffplay "rtsp://admin:Pass1234@36.226.49.159:554/rtspstream?channel=0&stream=1"



