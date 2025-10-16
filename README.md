#  Zerodha MCP Server - Advanced Trading & Analytics Platform

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![MCP](https://img.shields.io/badge/MCP-1.0+-green.svg)](https://modelcontextprotocol.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A cutting-edge **Model Context Protocol (MCP) server** for Zerodha Kite trading platform, featuring real-time market data streaming, advanced portfolio analytics, AI-powered trading strategies, and comprehensive risk management.

##  Features

###  Core Trading Features
- **Complete Zerodha Kite API Integration** - All trading operations supported
- **Real-time Market Data Streaming** - WebSocket-based live data feeds
- **Order Management** - Place, modify, cancel orders with risk validation
- **Portfolio Analytics** - Advanced metrics and performance analysis
- **Position Tracking** - Real-time P&L and exposure monitoring

###  AI-Powered Analytics
- **Technical Analysis** - RSI, MACD, Bollinger Bands, Moving Averages, ATR, Stochastic
- **Trading Strategies** - SMA Crossover, Mean Reversion, Momentum, Pairs Trading
- **Backtesting Engine** - Test strategies with historical data
- **Signal Generation** - Live trading signals with confidence scores
- **Risk Scoring** - AI-powered risk assessment

###  Advanced Risk Management
- **Position Size Limits** - Configurable maximum position sizes
- **Daily Loss Limits** - Automatic trading halt on loss thresholds
- **Portfolio Concentration** - Diversification monitoring
- **Correlation Analysis** - Detect correlated positions
- **Volatility Checks** - High-volatility stock warnings
- **Margin Utilization** - Real-time margin monitoring

###  Comprehensive Analytics
- **Portfolio Metrics** - Sharpe ratio, drawdown, volatility analysis
- **Performance Attribution** - Identify top/worst performers
- **Sector Analysis** - Portfolio sector allocation
- **Risk Decomposition** - Factor-based risk analysis
- **Correlation Matrix** - Position correlation analysis

###  Smart Alerts & Notifications
- **Price Alerts** - Custom price target notifications
- **Risk Alerts** - Automated risk threshold warnings
- **Performance Alerts** - Portfolio milestone notifications
- **Market Events** - Important market movement alerts

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.10 or higher
- Zerodha Kite API credentials
- VS Code with GitHub Copilot

### 1. Clone and Setup Environment

```bash
# Clone the repository
git clone <repository-url>
cd zerodha-mcp-server

# Create virtual environment
python -m venv .venv

# Activate virtual environment
# Windows:
.venv\\Scripts\\activate
# Linux/Mac:
source .venv/bin/activate

# Install dependencies
pip install -e .
```

### 2. Configure Environment Variables

```bash
# Copy example environment file
cp .env.example .env

# Edit .env file with your credentials
notepad .env  # Windows
nano .env     # Linux/Mac
```

Required environment variables:
```env
ZERODHA_API_KEY=your_api_key_here
ZERODHA_API_SECRET=your_api_secret_here
ZERODHA_ACCESS_TOKEN=your_access_token_here  # Optional
```

### 3. Install in VS Code

Create `.vscode/mcp.json` in your workspace:

```json
{
  "servers": {
    "zerodha-mcp-server": {
      "type": "stdio",
      "command": "python",
      "args": ["-m", "zerodha_mcp_server"]
    }
  }
}
```

##  Quick Start

### 1. Initialize Session

```python
# Using the MCP server in VS Code
initialize_session({
  "api_key": "your_api_key",
  "api_secret": "your_api_secret"
})
```

### 2. Get Market Data

```python
# Get real-time quotes
get_market_quotes({
  "instruments": ["NSE:RELIANCE", "NSE:TCS", "NSE:INFY"]
})

# Get historical data
get_historical_data({
  "symbol": "NSE:RELIANCE",
  "from_date": "2024-01-01",
  "to_date": "2024-12-31",
  "interval": "day"
})
```

### 3. Portfolio Analysis

```python
# Calculate portfolio metrics
calculate_portfolio_metrics({
  "include_risk_metrics": true,
  "include_performance": true,
  "timeframe": "1M"
})

# Technical analysis
technical_analysis({
  "symbol": "NSE:RELIANCE",
  "indicators": ["RSI", "MACD", "Bollinger", "SMA"],
  "period": 20
})
```

### 4. Trading Operations

```python
# Place an order
place_order({
  "symbol": "RELIANCE",
  "exchange": "NSE",
  "transaction_type": "BUY",
  "order_type": "LIMIT",
  "quantity": 10,
  "price": 2500,
  "product": "CNC"
})

# Set stop loss
set_stop_loss({
  "symbol": "RELIANCE",
  "stop_loss_price": 2400,
  "quantity": 10
})
```

### 5. Strategy Backtesting

```python
# Backtest a strategy
backtest_strategy({
  "strategy_name": "SMA_Crossover",
  "symbol": "NSE:RELIANCE",
  "start_date": "2024-01-01",
  "end_date": "2024-12-31",
  "initial_capital": 100000
})
```

##  Available Tools

###  Authentication
- `initialize_session` - Setup Kite API connection

###  Market Data
- `get_market_quotes` - Real-time market quotes
- `get_historical_data` - Historical OHLC data
- `search_instruments` - Find trading instruments

###  Trading
- `place_order` - Place buy/sell orders
- `modify_order` - Modify existing orders
- `cancel_order` - Cancel pending orders

###  Analytics
- `calculate_portfolio_metrics` - Portfolio analysis
- `technical_analysis` - Technical indicators
- `check_risk_limits` - Risk assessment

###  Strategy
- `backtest_strategy` - Strategy backtesting
- `get_live_signals` - Real-time trading signals

###  Alerts
- `setup_price_alert` - Price target alerts

##  Configuration Options

### Risk Management Settings
```python
{
  "max_position_size": 100000,      # Maximum position size
  "max_daily_loss": 10000,          # Daily loss limit
  "max_portfolio_concentration": 20, # Max % in single stock
  "max_leverage": 3.0               # Maximum leverage ratio
}
```

### Analytics Settings
```python
{
  "enable_streaming": true,         # Real-time data streaming
  "enable_analytics": true,         # Portfolio analytics
  "risk_management": true           # Risk checks
}
```

## 📊 Available Resources

Access portfolio and market data through MCP resources:

- `zerodha://profile` - User profile and account info
- `zerodha://portfolio` - Holdings and positions
- `zerodha://orders` - Order book
- `zerodha://positions` - Current positions
- `zerodha://margins` - Available margins
- `zerodha://analytics/portfolio` - Portfolio analytics
- `zerodha://analytics/risk` - Risk analysis
- `zerodha://market/quotes` - Market quotes

## 🧪 Testing & Development

### Run Tests
```bash
pytest tests/
```

### Development Mode
```bash
# Install in development mode
pip install -e .[dev]

# Run with debug logging
export LOG_LEVEL=DEBUG
python -m zerodha_mcp_server
```

### Code Formatting
```bash
# Format code
black src/
isort src/

# Type checking
mypy src/
```

##  Security Best Practices

1. **Never commit API credentials** to version control
2. **Use environment variables** for sensitive data
3. **Enable 2FA** on your Zerodha account
4. **Monitor API usage** regularly
5. **Use paper trading** for testing strategies
6. **Review risk limits** before live trading

##  Performance Optimization

- **Connection pooling** for API requests
- **Async operations** for parallel processing
- **Data caching** for frequently accessed data
- **WebSocket streaming** for real-time updates
- **Efficient data structures** for large datasets

##  Troubleshooting

### Common Issues

1. **Authentication Failed**
   - Check API key and secret
   - Verify access token validity
   - Ensure proper environment variables

2. **Rate Limiting**
   - Kite API has rate limits
   - Implement request throttling
   - Use WebSocket for real-time data

3. **Data Parsing Errors**
   - Verify instrument symbols format
   - Check date format (YYYY-MM-DD)
   - Validate numerical inputs

### Debug Mode
```bash
# Enable debug logging
export LOG_LEVEL=DEBUG
python -m zerodha_mcp_server
```

##  Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

##  Disclaimer

**This software is for educational and research purposes only. Trading in financial markets involves substantial risk of loss. The authors and contributors are not responsible for any financial losses incurred from using this software. Always test strategies thoroughly before using real money.**

##  Resources

- [Zerodha Kite API Documentation](https://kite.trade/docs/)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [MCP Python SDK](https://github.com/modelcontextprotocol/create-python-server)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)

##  Support

For support and questions:

1. Check the [FAQ section](#troubleshooting)
2. Search [existing issues](../../issues)
3. Create a [new issue](../../issues/new)
4. Join our [Discord community](#) (coming soon)

---

**Built with for the trading community**

** Star this repository if you find it useful!**
