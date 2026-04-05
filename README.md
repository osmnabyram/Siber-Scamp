# Scamp.py

A terminal-based Python tool developed for educational and laboratory purposes that accepts connections over TCP, captures keyboard inputs after an incoming connection, and forwards them to the remote host. The program operates with visual loading animation, ASCII banner display, and live listening indicator.

<img width="1187" height="745" alt="Screenshot 2026-01-07 234803" src="https://github.com/user-attachments/assets/faa71084-7d80-45b4-94d8-a6208a7a7da8" />

---

## Overview

When Scamp.py is executed, it begins listening on the specified port. When a client connection arrives, it accepts the connection and captures keyboard inputs, forwarding them in real-time over the socket. The interface is entirely terminal-based.

---

## Features

- Accept connections over TCP socket
- Live port listening animation
- ASCII banner display
- Real-time keyboard input capture
- Multi-threaded operation (animation + listening)
- Secure exit with Ctrl+C
- Error handling and clean shutdown

---

## Requirements

- Python 3.x
- `pynput` library

Installation:
```bash
pip install pynput
```

## Usage

To execute the tool:
```bash
python3 Scamp.py
```

## Default Settings

- HOST: `0.0.0.0`
- PORT: `8080`

---

## Program Startup

- System loading animation is displayed
- ASCII banner is printed
- Listening begins on the specified port

---

## Workflow

- Terminal screen is cleared
- Loading animation plays
- ASCII banner is displayed
- Socket is created and bound
- Listening begins on the port
- Live listening animation runs
- Client connection is accepted
- Listening animation stops
- Keyboard input capture begins
- Inputs are sent in real-time over the socket

---

## Technical Details

### Socket Structure

- `AF_INET / SOCK_STREAM`
- Single connection accepted
- Remains continuously active after connection is established

---

### Thread Usage

- Listening animation runs on a separate thread
- Main thread handles socket and keylogger operations

---

### Keylogger Mechanism

- `pynput.keyboard.Listener` is utilized
- Normal characters are written directly
- Special keys (ENTER, BACKSPACE, etc.) are labeled
- Collected data is transmitted over the socket

---

## Error and Exit Controls

- Program safely closes with Ctrl+C
- Program terminates on socket or thread errors
- Error messages are displayed in the terminal

---

## Security Notes

- This tool is designed exclusively for **educational**, **laboratory**, and **CTF** environments
- Execution on unauthorized systems or users is unethical and illegal
- Data transmitted over the network is **not encrypted**
