## Just For Backup

## Installation

First, you need to have Python 3.11 or higher installed. Then, you can install the required dependencies using pip:

```bash
pip install -r requirements.txt --upgrade
```

## How to get cookies.json
same as EdgeGPT https://github.com/acheong08/EdgeGPT#getting-authentication-required

## Usage

After saving `cookies.json` in current directory, you can run this project using the Python command line:

```bash
python main.py
```

Then, you can open `http://localhost:65432` in your browser to start chatting.

## Command Line Arguments

- `--host` or `-H`: The hostname and port for the server, default is `localhost:65432`.
- `--proxy` or `-p`: Proxy address, like `http://localhost:7890`, default is to use urllib to get proxy

## WebSocket API

The WebSocket API accepts a JSON object containing the following fields:

- `message`: The user's message.
- `context`: The context of the conversation, can be any string.

The WebSocket API returns a JSON object containing the following fields:

- `type`: The type of the message, can be the type from Bing response or `error`.
- `message`: The response from EdgeGPT.
- `error`: If an error occurs, this field will contain the error message.

## Server

If you want to deploy to the server, and use https protocol to access, then you need to change `websocket = new WebSocket(ws://${window.location.host}/ws/)` to `websocket = new WebSocket(wss://${window.location.host}/ws/)` in public/index.html
