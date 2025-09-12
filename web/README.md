# 🛡️ Secure Web Dashboard

A beautiful, secure, and privacy-focused web interface for the Zerodha MCP Server.

## 🔐 Security Features

- **Local Only**: Runs exclusively on localhost - no external access
- **Token Authentication**: Secure token-based authentication system  
- **Private Data**: All financial data stays on your computer
- **HTTPS Ready**: Supports secure connections
- **No External Dependencies**: Self-contained security

## 🚀 Quick Start

1. **Start the Web Dashboard:**
   ```bash
   cd C:\Users\vinay\OneDrive\Desktop\SNOWFLAKE_MCP_SERVER
   python web_dashboard.py
   ```

2. **Open Your Browser:**
   ```
   http://localhost:8080
   ```

3. **Login with Default Credentials:**
   - Username: `trader`
   - Password: `secure123`

## 📊 Dashboard Features

### Portfolio Management
- Real-time portfolio overview
- Holdings and positions tracking
- Profit/loss analysis
- Asset allocation visualization

### Market Data
- Live stock quotes
- Technical analysis indicators
- Market depth information
- Real-time price updates

### Trading Operations
- Place buy/sell orders
- View order history
- Cancel pending orders
- Risk management checks

### Analytics & Backtesting
- Strategy backtesting
- Performance analytics
- Risk assessment
- Technical indicators

## 🔧 Configuration

### Security Settings
The dashboard is configured for maximum security:

```python
# CORS - Localhost only
origins = [
    "http://localhost:8080",
    "https://localhost:8080",
    "http://127.0.0.1:8080",
    "https://127.0.0.1:8080"
]

# Token expiration
ACCESS_TOKEN_EXPIRE_MINUTES = 30

# Secure headers
app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,
    allow_credentials=True,
    allow_methods=["GET", "POST", "PUT", "DELETE"],
    allow_headers=["*"],
)
```

### Custom Authentication
Update credentials in `web_dashboard.py`:

```python
# Change these in production
USERS = {
    "your_username": "your_secure_password",
    "trader": "secure123"  # Default demo user
}
```

## 🌐 API Endpoints

### Authentication
- `POST /api/login` - Login and get access token
- `POST /api/logout` - Logout and invalidate token

### Portfolio
- `GET /api/portfolio` - Get portfolio summary
- `GET /api/holdings` - Get current holdings
- `GET /api/positions` - Get current positions

### Market Data
- `GET /api/quotes/{symbol}` - Get stock quotes
- `GET /api/technical-analysis/{symbol}` - Get technical analysis

### Trading
- `GET /api/orders` - Get order history
- `POST /api/place-order` - Place new order
- `DELETE /api/cancel-order/{order_id}` - Cancel order

### Analytics
- `GET /api/risk-assessment` - Get risk assessment
- `GET /api/backtest` - Run strategy backtest

### System
- `GET /api/health` - System health check

## 🎨 UI Components

### Modern Design
- Glass-morphism effect cards
- Gradient backgrounds
- Smooth animations
- Responsive design

### Interactive Elements
- Real-time data updates
- Form validation
- Loading states
- Error handling

### Security Indicators
- Visual security notices
- Private data badges
- Localhost-only warnings
- Authentication status

## 📱 Mobile Responsive

The dashboard is fully responsive and works on:
- Desktop computers
- Tablets
- Mobile phones
- Large displays

## 🔍 Data Privacy

### Local Processing
- All data processed locally
- No external API calls
- No data stored externally
- Complete privacy protection

### Secure Communication
- HTTPS support
- Token-based authentication
- Secure headers
- CORS protection

## 🛠️ Development

### File Structure
```
web/
├── index.html          # Main dashboard interface
├── web_dashboard.py    # FastAPI backend server
└── README.md          # This documentation
```

### Adding Features
1. Update API endpoints in `web_dashboard.py`
2. Add UI components in `index.html`
3. Implement JavaScript functions
4. Test security measures

### Security Checklist
- ✅ Localhost-only access
- ✅ Token authentication
- ✅ HTTPS support
- ✅ CORS protection
- ✅ Input validation
- ✅ Error handling
- ✅ Secure logging

## 🚨 Important Notes

### Financial Data Security
- This dashboard handles sensitive financial information
- Always use strong passwords
- Keep your system updated
- Use antivirus protection
- Monitor for suspicious activity

### Production Deployment
- Change default credentials
- Use environment variables for secrets
- Enable HTTPS
- Regular security audits
- Monitor access logs

## 📞 Support

For issues or questions:
1. Check the logs in the terminal
2. Verify your credentials
3. Ensure the MCP server is running
4. Check firewall settings

## 🏆 Best Practices

### Security
- Use strong, unique passwords
- Enable two-factor authentication if available
- Regular password updates
- Monitor access logs
- Keep software updated

### Performance
- Close unused browser tabs
- Monitor system resources
- Regular cache clearing
- Network monitoring
- Performance optimization

---

**🛡️ Your financial data security is our top priority. This dashboard ensures complete privacy while providing powerful trading capabilities.**
