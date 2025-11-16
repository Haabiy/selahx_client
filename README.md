# selahx_client
- Remote Access Tool — Fast and lightweight CLI experience.

- For educational purposes only.

[![Python](https://img.shields.io/badge/python-3.11%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
---

## Features

- Basic Commands: Navigate the system (ls, cd, pwd), clear terminal, exit, or terminate sessions.

- File Operations: Copy files/folders (cp, cpdir), remove files/folders (rm).

- Media Commands: Capture screenshots, webcam images, record audio or screen.

- System Commands: Control system functions (sleep, lock) and volume.

- Internet Commands: Perform web or YouTube searches directly.

![features](https://raw.githubusercontent.com/Haabiy/selahx_client/main/selahx/assets/slx_terminal.png)

---

## Usage

### Help

```bash
slx client --help
````

![features](https://raw.githubusercontent.com/Haabiy/selahx_client/main/selahx/assets/slx_client_help.png)

```bash
slx save --help
````

![features](https://raw.githubusercontent.com/Haabiy/selahx_client/main/selahx/assets/slx_client_help.png)

### Client

Start a client and connect to the server:

```bash
slx client --username user --port 1221
```

**Options:**

* `--username` — Username for the client session
* `--port` — Server port to connect to

---

### Transfer files from EC2 to Local

Start saving files:

```bash
slx save --key-file key.pem --user ubuntu --host ec2-xx-xx-xx-xx.compute-1.amazonaws.com --dest ~/Downloads/test
```

**Options:**

* `--key-file` — Path to the SSH private key
* `--user` — `ubuntu` (user for `ubuntu@ec2-xx-xx-xx-xx.compute-1.amazonaws.com`)
* `--host` — EC2 host (everything after `@`)
* `--dest` — Destination folder
* `~/Downloads/test` — Example local destination path

![features](https://raw.githubusercontent.com/Haabiy/selahx_client/main/selahx/assets/ec2_user_host.png)

---

## Example Workflow

1. Launch the server:

- server package: https://pypi.org/project/selahx_server

- github: https://github.com/Haabiy/selahx_server

```bash
slx --key-file key.pem --port 1221 --ssh-host ubuntu@ec2-xx-xx-xx-xx.compute-1.amazonaws.com
```

2. Connect a client from your local machine:

```bash
slx client --username user --port 1221
```

Once connected, a reverse SSH tunnel is automatically established.

---

## Requirements

* Python 3.11+
* Dependencies are managed via Poetry (see `pyproject.toml`)

---