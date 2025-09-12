<!-- Use this file to provide workspace-specific custom instructions to Copilot. For more details, visit https://code.visualstudio.com/docs/copilot/copilot-customization#_use-a-githubcopilotinstructionsmd-file -->

# Zerodha MCP Server - GitHub Copilot Instructions

This is an advanced Model Context Protocol (MCP) server for Zerodha Kite trading platform with cutting-edge features including:

- **Real-time market data streaming** with WebSocket connections
- **Advanced portfolio analytics** and risk management
- **AI-powered trading strategies** with backtesting capabilities
- **Comprehensive risk management** system
- **Technical analysis** tools and indicators
- **Automated alerts** and notifications

## Key Technologies Used

- **MCP (Model Context Protocol)**: For seamless integration with AI assistants
- **Zerodha Kite API**: Official trading API integration
- **AsyncIO**: For high-performance asynchronous operations
- **Pandas/NumPy**: For data analysis and calculations
- **WebSockets**: For real-time market data streaming
- **Pydantic**: For data validation and settings management

## Code Style and Patterns

1. **Use async/await** for all I/O operations
2. **Type hints** are mandatory for all functions
3. **Error handling** should be comprehensive with proper logging
4. **Pydantic models** for data validation
5. **Dataclasses** for simple data structures
6. **Logging** should be used extensively for debugging

## MCP Server Architecture

- **Tools**: Implement trading operations, analysis, and utilities
- **Resources**: Provide access to portfolio data, market data, and analytics
- **Server**: Main MCP server class with proper initialization

## Important Notes

- Always validate user inputs for trading operations
- Implement proper risk checks before executing trades
- Use appropriate error handling for network operations
- Maintain thread safety for concurrent operations
- Follow Zerodha API rate limits and best practices

## References

- MCP Documentation: https://modelcontextprotocol.io/llms-full.txt
- MCP Python SDK: https://github.com/modelcontextprotocol/create-python-server
- Zerodha Kite API: https://kite.trade/docs/

## Security Considerations

- Never commit API keys or secrets to version control
- Use environment variables for sensitive configuration
- Implement proper authentication and authorization
- Validate all user inputs to prevent injection attacks
- Use secure WebSocket connections for streaming data

When working on this project, prioritize security, performance, and user experience. Always test trading operations in a safe environment before using with real money.
