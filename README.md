# Distributed Network Computing System

<div align="center">
  
![Java Version](https://img.shields.io/badge/Java-17%2B-orange)
![TCP/IP](https://img.shields.io/badge/Protocol-TCP%2FIP-blue)
![License](https://img.shields.io/badge/License-MIT-green)
  
**A powerful client-server framework for distributed computing and remote execution**
</div>

## 🌟 System Architecture

The Distributed Network Computing System implements a client-server architecture that enables distributed calculation and remote command execution across virtual machines.

```
                               ┌─────────────────────┐
                               │      TCP/IP         │
                               │    CONNECTION       │
                               └─────────────────────┘
                                         │
                                         ▼
┌───────────────────────┐      ┌─────────────────────┐
│       CLIENT VM        │◄────►│      SERVER VM      │
│    192.168.48.130      │      │   192.168.48.128    │
└───────────────────────┘      └─────────────────────┘
          │                               │
          ▼                               ▼
┌───────────────────────┐      ┌─────────────────────┐
│    CLIENT FEATURES    │      │   SERVER FEATURES   │
│  - Interactive UI     │      │ - Thread Pool       │
│  - Calculator Mode    │      │ - Task Splitting    │
│  - Command Mode       │      │ - Parallel Execution│
└───────────────────────┘      └─────────────────────┘
```

## ✨ Features

### Distributed Calculator
- Process complex mathematical expressions
- Parse and tokenize mathematical expressions
- Handle operator precedence (parentheses, multiplication/division, addition/subtraction)
- Split calculations for parallel execution
- Return formatted results in real-time

### Remote Command Execution
- Execute system commands on the server machine
- Run commands in dedicated threads
- Capture both stdout and stderr output
- Return complete command results to the client
- Support for Windows and Linux commands

### Technical Highlights
- **Concurrency**: Thread pool for efficient resource management
- **Resilience**: Comprehensive error handling and reporting
- **UI**: ASCII-decorated console interface for improved readability
- **Communication**: Efficient TCP/IP socket implementation

## 💻 System Requirements

### Server (VM 1)
- **IP Address**: 192.168.48.128
- **Operating System**: Linux or Windows (VMware Workstation)
- **Java**: JDK 8 or higher
- **Network**: Configured for VMware networking
- **Memory**: 1GB minimum

### Client (VM 2)
- **IP Address**: 192.168.48.130
- **Operating System**: Linux or Windows (VMware Workstation)
- **Java**: JDK 8 or higher
- **Network**: Configured for VMware networking
- **Memory**: 512MB minimum

## 🚀 Installation & Setup

### Server Setup (192.168.48.128)

1. **Download** the server files
2. **Navigate** to the project directory
3. **Compile** the server:
   ```bash
   javac Server.java
   ```
4. **Run** the server:
   ```bash
   java Server
   ```
5. **Verify** successful startup with the welcome banner:
   ```
   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
   ┃                         DISTRIBUTED SERVER v1.0                              ┃
   ┃                  IP: 192.168.48.128 • PORT: 1234                            ┃
   ┣━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┫
   ┃  Features:                                                                  ┃
   ┃  • Distributed Calculator - Process mathematical expressions                ┃
   ┃  • Remote Command Execution - Run system commands                           ┃
   ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛
   ```

### Client Setup (192.168.48.130)

1. **Download** the client files
2. **Navigate** to the project directory
3. **Compile** the client:
   ```bash
   javac Client.java
   ```
4. **Run** the client:
   ```bash
   java Client
   ```
5. **Verify** successful startup with the client menu:
   ```
   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
   ┃                         DISTRIBUTED CLIENT v1.0                              ┃
   ┃          Client IP: 192.168.48.130 • Server IP: 192.168.48.128              ┃
   ┣━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┫
   ┃  Features:                                                                  ┃
   ┃  • Distributed Calculator - Process mathematical expressions                ┃
   ┃  • Remote Command Execution - Run system commands                           ┃
   ┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛
   ```

## 📝 Usage Guide

### Distributed Calculator

1. Start both server and client applications
2. Select option `1` from the client menu
3. Enter a mathematical expression, such as:
   - `(12 + 8) * 3 - 4/2`
   - `5.2*3+(10-2)/4`
   - `(7-2)*(4+3)/2`
4. View the calculated result

**Example:**
```
┏━━━━━ Distributed Calculator Mode ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┃ ℹ️  Enter mathematical expressions to evaluate
┃ ℹ️  Examples: '(12 + 8) * 3 - 4 / 2' or '10 + 5 * 3'
┃ ℹ️  Type 'back' to return to the main menu

Enter expression: (12 + 8) * 3 - 4/2
┃ ℹ️  Sending to server: (12 + 8) * 3 - 4/2
┃ ✅ Result: 58
```

### Remote Command Execution

1. Start both server and client applications
2. Select option `2` from the client menu
3. Enter a system command, such as:
   - `ls -la` (Linux) or `dir` (Windows)
   - `echo "Hello World"`
   - `cat /etc/hostname` (Linux) or `hostname` (Windows)
4. View the command output

**Example:**
```
┏━━━━━ Remote Command Execution Mode ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┃ ℹ️  Enter commands to execute on the server
┃ ℹ️  Examples: 'ls -la', 'dir', 'ping localhost'
┃ ℹ️  Type 'back' to return to the main menu

Enter command: ls -la
┃ ℹ️  Sending command to server: ls -la
┃ ℹ️  Waiting for command execution...
┏━━━━━ Command Output ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
┃ total 16
┃ drwxr-xr-x 2 user user 4096 May 11 10:23 .
┃ drwxr-xr-x 5 user user 4096 May 11 10:20 ..
┃ -rw-r--r-- 1 user user 2104 May 11 10:23 Client.java
┃ -rw-r--r-- 1 user user 3782 May 11 10:23 Server.java
```

## 🧠 How It Works

### Distributed Calculator

The calculator implements a multi-stage process for expression evaluation:

1. **Expression Parsing**: The server parses the mathematical expression into tokens
2. **Work Division**: Complex expressions are split into sub-expressions
3. **Parallel Processing**: Each sub-expression is evaluated in its own thread
4. **Result Aggregation**: Individual results are combined into the final answer

### Remote Command Execution

The command execution implements a streamlined process:

1. **Command Reception**: The server receives the command from the client
2. **Process Creation**: A new process is created using ProcessBuilder
3. **Output Capture**: Separate threads capture stdout and stderr
4. **Result Transmission**: Complete output is sent back to the client

## 🔧 Troubleshooting

### Common Issues

| Issue | Possible Cause | Solution |
|-------|----------------|----------|
| Connection refused | Server not running | Start the server application |
| Address already in use | Port 1234 is occupied | Check for processes using port 1234 |
| Server host not found | Network configuration issue | Verify IP addresses and network connectivity |
| Expression calculation error | Invalid expression syntax | Check the expression format |
| Command execution error | Command not found on server | Verify the command is available on the server |

### Finding Port Usage

**Windows**:
```
netstat -ano | findstr :1234
```

**Linux**:
```
lsof -i :1234
```

## ⚙️ Advanced Configuration

### Customizing IP Addresses

If you need to use different IP addresses, modify the following:

1. In `Client.java`, update:
   ```java
   private static final String SERVER_IP = "192.168.48.128";
   ```

2. In `Server.java`, update:
   ```java
   serverSocket = new ServerSocket(1234, 50, InetAddress.getByName("192.168.48.128"));
   ```

### Thread Pool Configuration

To adjust concurrency levels, modify the thread pool size in `Server.java`:

```java
private static final ExecutorService threadPool = Executors.newFixedThreadPool(5);
```

## ⚖️ License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<div align="center">
  
**Distributed Network Computing System**
  
*Created for Advanced Socket Programming Demonstration*
  
Copyright © 2025 All Rights Reserved
</div>