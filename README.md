# Portable Wireless IDE

A self-contained wireless development environment for embedded systems that requires zero infrastructure. Transform any microcontroller into its own WiFi hotspot serving a complete web-based IDE accessible from any browser.

## Overview

This project eliminates the need for network infrastructure when developing embedded code in field environments. The microcontroller creates its own WiFi hotspot and serves a professional web-based integrated development environment (IDE) that includes:

- **File Editor**: Load, edit, and save CircuitPython files with syntax highlighting
- **Console Monitor**: Real-time console output and interactive Python REPL
- **File Browser**: Complete filesystem management (create, delete, organize files)
- **Live Development**: Auto-reboot on `code.py` save for immediate testing

Perfect for field research, remote deployment, educational environments, or anywhere network access is limited or unavailable.

## Features

### 🌐 Zero Infrastructure Required
- Creates open WiFi hotspot (no password needed)
- Self-contained web server
- Works with any device that has a browser
- No internet connection required

### 💻 Complete Development Environment
- Web-based file editor with monospace fonts
- Real-time console monitoring
- Interactive Python command execution
- File management system
- Automatic code reloading

### 🔧 Professional Workflow
- Save files and see changes immediately
- Monitor console output in real-time
- Send commands and see live responses
- Manage multiple project files
- Professional tabbed interface

### 📱 Universal Access
- Works on laptops, tablets, phones
- Any modern browser supported
- Responsive design for all screen sizes
- Touch-friendly interface

## Hardware Requirements

- **Raspberry Pi Pico 2 W** (RP2350 recommended)
  - Or any CircuitPython-compatible board with WiFi
- **USB cable** for initial setup
- **Computer** for initial file upload

## Software Requirements

- **CircuitPython 9.2.7 or later**
- **adafruit_httpserver library**

## Quick Start

### 1. Prepare Hardware
1. Install CircuitPython on your Pico 2 W
2. Download `adafruit_httpserver` library to `/lib` folder on CIRCUITPY drive

### 2. Install Code
1. Download `code.py` from this repository
2. Copy to the root of your CIRCUITPY drive
3. Microcontroller will automatically reboot and start the system

### 3. Connect and Use
1. **Connect to WiFi**: Look for "PicoTest" network (open, no password)
2. **Open Browser**: Navigate to `http://192.168.4.1`
3. **Start Developing**: Use the tabbed interface to edit files and monitor console

## Usage Guide

### File Editor Tab
- **Load File**: Enter filename and click "Load File"
- **Save File**: Enter filename, paste/edit code, click "Save File"
- **Auto-Reboot**: Saving `code.py` automatically reboots the device
- **Clear Editor**: Reset filename and content fields

### Console Monitor Tab
- **Start Monitoring**: Click to begin real-time console output
- **Send Commands**: Type Python commands and execute them live
- **Interrupt**: Send Ctrl+C signal to running code
- **Clear Display**: Reset the console view

### File Browser Tab
- **Refresh**: Update the file list
- **Select Files**: Click on any file to select it
- **Load Selected**: Switch to editor with selected file loaded
- **Delete Files**: Remove selected files (cannot delete running `code.py`)
- **Create New**: Make new empty files

## Network Configuration

- **SSID**: PicoTest
- **Password**: None (open network)
- **IP Address**: 192.168.4.1
- **Subnet**: 255.255.255.0
- **Gateway**: 192.168.4.1

## Example Development Workflow

1. **Connect** to PicoTest WiFi network
2. **Open** browser to http://192.168.4.1
3. **Load** existing code or start new file
4. **Edit** code in the web editor
5. **Save** file (auto-reboot if code.py)
6. **Monitor** console output in real-time
7. **Debug** using interactive commands
8. **Iterate** quickly with live reloading

## Troubleshooting

### Cannot Connect to WiFi
- Ensure device has powered up completely (wait 30 seconds)
- Look for "PicoTest" in available networks
- Try forgetting and reconnecting to the network

### Cannot Access Web Interface
- Verify IP address: http://192.168.4.1
- Try http://192.168.4.1:80 explicitly
- Clear browser cache and try again
- Ensure no VPN is interfering

### Code Changes Not Taking Effect
- Verify you saved `code.py` (not another filename)
- Wait for automatic reboot (2-3 seconds)
- Check console monitor for error messages
- Ensure file was saved successfully

### Console Not Updating
- Click "Start Monitoring" button
- Refresh the browser page
- Check that code is producing output

## Known Issues

- **Chrome Browser**: "Clear Editor" may not fully clear filename field due to Chrome's form history feature. Manually delete filename text before entering new names.
- **Large Files**: Very large files (>100KB) may load slowly over WiFi
- **Multiple Users**: Designed for single developer use; multiple simultaneous users may cause conflicts

## Technical Details

### Architecture
- **Web Server**: Custom HTTP server using adafruit_httpserver
- **Frontend**: Pure HTML/CSS/JavaScript (no frameworks)
- **Communication**: REST API with JSON responses
- **File System**: Direct CircuitPython filesystem access
- **Networking**: WiFi access point mode with custom IP configuration

### Security Notes
- **Open Network**: No password protection for ease of use
- **Local Only**: No internet routing, isolated network
- **File Access**: Full filesystem access through web interface
- **No Encryption**: HTTP only (not HTTPS)

Suitable for development and testing environments. Not recommended for production deployment without additional security measures.

## Applications

### Field Research
- Environmental monitoring stations
- Remote sensor deployment
- Scientific instrument programming
- Data collection system setup

### Education
- Classroom programming exercises
- Student project development
- No network infrastructure required
- Works with any student device

### Rapid Prototyping
- Quick hardware testing
- Firmware development
- IoT project iteration
- Embedded system debugging

### Remote Deployment
- Field programming of devices
- Configuration updates
- System maintenance
- Emergency fixes

## Contributing

Contributions welcome! This project aims to make embedded development more accessible and field-friendly.

### Areas for Enhancement
- Additional microcontroller support
- Enhanced syntax highlighting
- File upload/download features
- Multi-user support
- Security improvements

## License

MIT License - see LICENSE file for details.

## Citation

If you use this work in academic research, please cite:

```
[Citation will be added upon publication]
```

## Related Work

This project builds upon:
- CircuitPython ecosystem
- Adafruit libraries
- Web-based development concepts
- Embedded systems accessibility

## Contact

Questions, bug reports, and feature requests: [GitHub Issues](https://github.com/saladmachine/portable-wireless-ide/issues)

---

**Transform any location into a development environment. No infrastructure required.**
