"""
# Triangular Arbitrage Bot

This Python script implements a Triangular Arbitrage Bot using the CCXT library to interact with various cryptocurrency exchanges. The bot scans the markets for arbitrage opportunities across different trading pairs and automatically executes trades to take advantage of price discrepancies.

The bot supports exchanges such as Binance, Kucoin, Okex, and Huobi. It utilizes the CCXT library to fetch market data, place orders, and calculate price impacts. The bot considers fees and tick sizes when executing trades. Additionally, the bot takes into account the impact of its orders on the current order book to avoid profitable trades only theoretically.

It uses a triangular arbitrage strategy, where it identifies The bot searches through all possible triangular opportunities on each exchange that start with USDT as the quote currency (e.g., BTC/USDT, ETH/USDT, BTC/ETH) and looks for opportunities where the cumulative profits of the trades are above a specified threshold. 

The bot sends notifications to a Telegram chat with details of profitable trades, including the trading pairs, profit percentage, and executed trades. It logs all activities in the 'arbitrage.log' file.

To use the bot, you need to set up API keys for the supported exchanges and provide them in a 'config.env' file. You also need to specify the initial amount of USDT to trade.



## Disclaimer

- The code provided is for educational and informational purposes only. Use it at your own risk.
- Triangular arbitrage can be risky and complex. Make sure you understand the risks involved and do thorough testing before using the bot with real funds.
- The bot's performance and profitability may vary depending on market conditions and exchange limitations.

## Prerequisites

- Python 3.7 or higher
- CCXT library (`ccxt` package)
- `dotenv` library (`python-dotenv` package)
- `pandas` library (`pandas` package)
- `numpy` library (`numpy` package)
- `telegram` library (`python-telegram-bot` package)

## Installation

1. Clone the repository:  -git clone https://github.com/your-username/triangular-arbitrage-bot.git

2. Install the required dependencies using pip

3. Set up API keys and other configuration parameters:

4. Rename the `config.env.example` file to `config.env`.

 5. Open the `config.env` file and replace the placeholders with your actual API keys and telegram bot token.

## Usage

1. Run the script:  python tri_arb_bot.py
2. The bot will start scanning for triangular arbitrage opportunities across the configured exchanges.
3. Once an arbitrage opportunity is found and meets the specified criteria, the bot will execute the trades automatically.
4. The bot will send notifications to a Telegram chat with the details of profitable trades.
5. The bot will log all activities in the `arbitrage.log` file.

## Configuration

- Adjust the `min_message_interval` variable to set the minimum time between messages sent to the Telegram Bot for each trading pair.
- Modify the fees for each exchange by updating the respective fee variables (`binance_fee`, `kucoin_fee`, `okx_fee`, `huobi_fee`).
- Customize the profit percentage threshold in the `find_triangular_arbitrage_opportunities` function to filter opportunities.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. If you use or modify this code, please provide attribution by citing the original work.


## Contact

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request on GitHub.
"""
