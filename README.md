# RTSP Kit (`rtspkit`)

[![PyPI Version](https://img.shields.io/pypi/v/rtspkit.svg)](https://pypi.org/project/rtspkit/)
[![Python Versions](https://img.shields.io/pypi/pyversions/rtspkit.svg)](https://pypi.org/project/rtspkit/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**RTSPKit is a powerful vulnerable CCTV & WebCam finder, stream validator, and exposer.** It is a high-performance network scanner designed to discover, validate, audit credentials, render multi-camera video feeds, and record live RTSP video streams across IP networks.

---

## Key Features

- **Parallel Port & Stream Validation**: High-concurrency network socket scan and RTSP stream verification.
- **RTSP Subpath Probing**: Automatic route scanning for popular IP camera routes (`/h264`, `/live/ch0`, `/stream1`, `/onvif1`, etc.).
- **Credential Brute-Forcing**: Custom credential pair testing and dictionary attack modes for locked camera streams.
- **Non-Blocking Multi-Camera Grid View**: Real-time Picture-in-Picture (PiP) layout renderer powered by background frame readers.
- **Stream Recording Mode**: Timed or manual on-demand recording of live RTSP streams to `.mp4` video files.
- **VLC Integration**: Launch streams directly inside external VLC Media Player.
- **Metadata Extraction & Export**: Automatically logs video resolution and FPS metadata to JSON, CSV, or TXT formats.
- **CLI & Python API**: Fully operational as both a command-line tool (`rtspkit`) and a Python library module (`import rtspkit`).

---

## Installation

Install `rtspkit` directly from PyPI using `pip`:

```bash
pip install rtspkit
```

---

## Quickstart & Usage

### 1. Command Line Interface (CLI)

#### Interactive Mode (Wizard)
Run `rtspkit` without positional parameters to open the step-by-step interactive setup wizard:
```bash
rtspkit
```

#### Basic Subnet Scan & Multi-Camera Grid View
Scan a `/24` subnet and launch a 3-column PiP video grid:
```bash
rtspkit 192.168.1.0/24
```

#### Path Probing & Dictionary Brute-Force
Probe common RTSP paths and execute credential brute-forcing:
```bash
rtspkit 192.168.1.0/24 --probe-paths -b -U usernames.txt -P passwords.txt -o results.json
```

#### Single Camera Inspector Mode
Interactive stream reader (`n` = next, `p` = previous, `s` = screenshot, `r` = record, `q` = quit):
```bash
rtspkit 192.168.1.0/24 --mode single
```

#### Record Live Streams
Record active streams for 30 seconds:
```bash
rtspkit 192.168.1.50 --mode record --rec-duration 30
```

---
