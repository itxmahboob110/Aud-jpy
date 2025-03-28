# AUD/JPY MT5 Signal Bot

A Telegram bot that provides trading signals for AUD/JPY using MetaTrader 5 data.

## Features

- Real-time signals for multiple timeframes (1m, 5m, 15m, 1h)
- Technical analysis using SMA, RSI, MACD, and Stochastic
- Confidence scoring and accuracy estimates
- Performance tracking

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Install TA-Lib (may require additional steps):
   ```bash
   # For Windows: Download from https://www.lfd.uci.edu/~gohlke/pythonlibs/#ta-lib
   # For Linux/Mac: brew install ta-lib or sudo apt-get install ta-lib
   ```

## Configuration

1. Edit `config.ini` with your credentials:
   ```ini
   [MT5]
   account_number = YOUR_MT5_ACCOUNT
   password = YOUR_MT5_PASSWORD
   server = YOUR_MT5_SERVER
   
   [Telegram]
   token = YOUR_TELEGRAM_BOT_TOKEN
   ```

2. Alternatively, use `.env` file for environment variables

## Usage

```bash
python bot.py
```

## Deployment

For 24/7 operation, deploy to a cloud server:

1. **VPS Setup** (Recommended):
   ```bash
   # Install required system packages
   sudo apt update
   sudo apt install python3-pip python3-venv
   
   # Create virtual environment
   python3 -m venv venv
   source venv/bin/activate
   
   # Install dependencies
   pip install -r requirements.txt
   
   # Run in background
   nohup python bot.py > bot.log 2>&1 &
   ```

2. **Docker Setup**:
   ```dockerfile
   FROM python:3.9-slim
   WORKDIR /app
   COPY . .
   RUN pip install -r requirements.txt
   CMD ["python", "bot.py"]
   ```

## Troubleshooting

- **MT5 Connection Issues**: Verify server name and credentials
- **TA-Lib Errors**: Ensure TA-Lib is properly installed
- **Telegram Errors**: Check bot token and chat permissions
