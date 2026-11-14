# Wyckoff Bot Signal #

A lightweight, rule-based market analysis tool inspired by Richard D. Wyckoff's trading methodology, designed to analyze Gold (GC=F) price movements and identify potential BUY, SELL, or WAIT opportunities.

Overview

This project implements a simple workflow based on Wyckoff's theory, targeting the gold market.

The objective is to analyze price action and volume, identify potential market structures, and generate trading signals based on predefined conditions.

How does it work?

The project follows a straightforward workflow:

Market Scraper (market)
Fetches Gold market data through Yahoo Finance.
Retrieves OHLCV (Open, High, Low, Close, Volume) data.
Converts and stores the response in JSON format.
Updates market data using 15-minute candles.
Wyckoff Analyzer (wyckoff)
Processes the collected JSON data.
Calculates support and resistance levels.
Analyzes relative volume.
Identifies potential Wyckoff events.
Generates BUY, SELL, or WAIT signals.
Startup Program (start)
Coordinates the scraper and analyzer.
Refreshes the analysis every 60 seconds.
Continuously monitors available market data.
Trading Signals

The analyzer currently looks for the following conditions:

Signal	Description
BUY	Potential bullish breakout / Sign of Strength (SOS)
SELL	Potential bearish breakdown / Sign of Weakness (SOW)
BUY CANDIDATE	Potential Spring
SELL CANDIDATE	Potential Upthrust
WAIT	No qualifying trading condition detected

Note: These are rule-based, Wyckoff-inspired signals, not guaranteed confirmations of genuine Wyckoff market phases.

Requirements

The following dependencies are required:

Bash – A relatively recent version is recommended.
AWK – mawk or gawk (the script has been tested with compatible AWK implementations).
jq – JSON parsing and data extraction.
curl – Fetching market data from Yahoo Finance.


Installation

Clone the repository

Navigate into the project directory

Make the scripts executable

To start the bot, simply execute: './start'


The program will start immediately and continuously:
Fetch market data.
Update the JSON dataset.
Run the Wyckoff analyzer.
Display the latest trading recommendation.
Repeat the process every 60 seconds.

Configuration

The refresh intervals and market data settings can be adjusted directly in the scripts

You can modify these values to experiment with different timeframes and analysis parameters.

Important: Refreshing the analyzer every minute does not mean Yahoo Finance provides a new 15-minute candle every minute. The current candle may still be forming.

Disclaimer

Market conditions can change rapidly, and false signals are possible.

Always perform independent analysis and backtesting before making trading decisions.

License: MIT 
