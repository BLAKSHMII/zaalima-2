README.md

Project: Photon – Real-Time WebSocket Stock Ticker

📌 Overview

Photon is a real-time stock ticker web application built using Flask and WebSockets.
It pushes live stock price updates to the browser without page refresh.

🛠️ Tech Stack

Backend: Python, Flask, Flask-SocketIO

Async Engine: Eventlet

Frontend: HTML, CSS, JavaScript

Protocol: WebSocket

API (Week-4): Finnhub / Alpaca (optional)

📁 Project Structure
photon/
│
├── app.py
├── config.py                # Week-4
├── streamer/
│   ├── stock_streamer.py    # Week-2
│   └── real_streamer.py     # Week-4
└── templates/
    └── index.html

🗓️ WEEK-1: WebSocket Connection Setup
🎯 Objective

Establish a real-time WebSocket connection between browser and Flask server.

🔹 Implementation

Flask server setup

Flask-SocketIO integration

Client connects and receives confirmation message

🔹 Output

Browser successfully connects to server

Console shows “WebSocket Connected”

🔹 Key Learning

✔ WebSocket handshake
✔ Event-based communication

🗓️ WEEK-2: Mock Live Stock Streaming
🎯 Objective

Stream live (mock) stock prices every second.

🔹 Implementation

Background task generates random stock prices

Server broadcasts data to all connected clients

Frontend updates UI dynamically

🔹 Output
AAPL : $152.43
TSLA : $278.11
GOOGL : $198.65
(Updated every second)

🔹 Key Learning

✔ Background tasks
✔ Real-time data push
✔ No page refresh

🗓️ WEEK-3: Subscription & UI Enhancements
🎯 Objective

Send only selected stock updates to users.

🔹 Implementation

Room-based subscription using join_room()

Client subscribes to specific tickers

Server emits updates to specific rooms

Green/Red color indicators for price changes

🔹 Output

Only subscribed stocks update

Prices flash green or red based on change

🔹 Key Learning

✔ WebSocket rooms
✔ Scalable broadcasting
✔ Better UX

🗓️ WEEK-4: Real Stock API & Production Readiness
🎯 Objective

Replace mock data with real stock market data.

🔹 Implementation

Integration with real API (Finnhub / Alpaca)

Secure API key management

Error handling for API failures

Controlled update intervals

🔹 Output

Real-time market prices

Stable WebSocket connection

Production-ready architecture

🔹 Key Learning

✔ External API integration
✔ Error handling
✔ Production best practices

🔄 Execution Flow
User opens browser
   ↓
WebSocket connection established
   ↓
User subscribes to stock
   ↓
Server fetches stock data
   ↓
Data broadcast to room
   ↓
UI updates instantly

▶️ How to Run
pip install flask flask-socketio eventlet requests
python app.py


Open:

http://127.0.0.1:5000
Browser opens
   ↓
WebSocket connection created
   ↓
User subscribes to stock
   ↓
Server fetches price from Finnhub API
   ↓
Price sent via WebSocket room
   ↓
UI updates instantly
