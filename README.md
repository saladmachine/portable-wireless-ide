# Portable Wireless Development Platform

Transform any smartphone or tablet into a powerful interface for embedded systems development and field instrumentation. This revolutionary platform eliminates expensive displays, connectors, and keyboards by leveraging the sophisticated computing device you already carry in your pocket.

## The Problem We Solve

Traditional field instruments and embedded development setups cost $200-500 in interface hardware alone:
- **Ruggedized connectors**: $75-150 each
- **Small displays**: $50-100 each  
- **Input devices**: $25-75 each
- **Integration costs**: $50-100 each

**Meanwhile, everyone carries a $500+ computer with a superior display, input system, and wireless connectivity.**

## Our Solution

This platform creates a self-contained wireless development environment that uses YOUR devices as the interface. The microcontroller becomes its own WiFi hotspot serving a complete web-based integrated development environment (IDE) that includes:

- **File Editor**: Load, edit, and save CircuitPython files with syntax highlighting
- **Console Monitor**: Real-time console output and interactive Python REPL
- **File Browser**: Complete filesystem management (create, delete, organize files)
- **Live Development**: Auto-reboot on `code.py` save for immediate testing

## Why This Approach Works

### The Smartphone Revolution
Modern smartphones and tablets are incredibly sophisticated:
- **Processing power**: Often exceeds desktop computers from just a few years ago
- **Display quality**: High resolution, color, touch-sensitive
- **User interface**: Familiar, intuitive, highly responsive
- **Connectivity**: WiFi, cellular, Bluetooth built-in
- **Battery life**: All-day operation
- **Ubiquity**: Nearly everyone has one

### Traditional Approach Problems
Embedded systems typically add:
- Small, expensive displays with poor visibility
- Limited input methods (tiny buttons, membrane keyboards)  
- Expensive ruggedized connectors prone to failure
- Custom interfaces requiring training
- High per-unit costs limiting deployment
- Single-purpose hardware with limited functionality

### Our Solution Benefits
- **Leverage existing hardware**: Use the $500+ computer everyone carries
- **Superior interface**: Better than any custom embedded display
- **Zero additional cost**: No interface hardware to purchase
- **Universal compatibility**: Works with any modern device
- **Familiar operation**: Web browser interface everyone knows
- **Future-proof**: Interface improves as user devices improve

## Revolutionary Cost Savings

**Traditional Approach:**
- Embedded controller: $10-20
- Ruggedized connector: $75-150
- Display module: $50-100
- Keypad/interface: $25-75
- Integration/enclosure: $50-100
- **Total: $210-445 per device**

**Our Approach:**
- Development platform: <$50
- User's existing phone/tablet: $0 (already owned)
- **Total: <$50 per device (~75%-90% cost reduction)**

### Why This Makes Sense

Your smartphone already has:
- ✅ High-resolution touchscreen display
- ✅ Intuitive touch interface
- ✅ Powerful processor and memory
- ✅ WiFi connectivity
- ✅ Long battery life
- ✅ Familiar user interface

Why duplicate all this with expensive specialized hardware?

## Hardware Requirements

**Development Platform:**
- **Raspberry Pi Pico 2 W** (RP2350 with integrated WiFi)
- **Adafruit Proto Doubler PiCowbell** (pin access and prototyping)
- **Acrylic mounting plates** (clear construction, all connections visible)
- **Total cost: ~$20** (vs $200-400 for traditional instrument interfaces)

**User Interface:**
- Any device with a modern web browser
- Smartphone, tablet, laptop, or desktop
- **No additional hardware purchase required**
- **No software installation needed**

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
- Environmental monitoring stations without expensive displays
- Remote sensor deployment and configuration  
- Scientific instrument control using researcher's own devices
- Data collection systems with universal accessibility

### Education
- Eliminate computer lab requirements and software installation
- Students use their own phones/tablets for embedded programming
- No licensing costs or compatibility issues
- Works anywhere - classroom, home, library, outdoors

### Rapid Prototyping  
- Instant access to all microcontroller pins for sensor integration
- Quick hardware testing without specialized interfaces
- Custom instrument development using familiar web interfaces
- IoT project iteration with immediate wireless access

### Cost-Sensitive Applications
- Replace expensive instrument interfaces with $20 platform
- Leverage existing user hardware instead of duplicating functionality
- Perfect for developing regions and budget-constrained projects
- Educational institutions with limited technology budgets

### Professional Development
- Field programming and debugging without infrastructure
- Custom laboratory automation interfaces
- Portable instrument control for service technicians
- Emergency firmware updates in remote locations

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

## Contact

Questions, bug reports, and feature requests: [GitHub Issues](https://github.com/saladmachine/portable-wireless-ide/issues)

---

**Stop duplicating hardware. Start leveraging what users already have.**  
**Transform any location into a development environment. No infrastructure required.**
