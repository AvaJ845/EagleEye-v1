# EagleEye-v1
Educational and analytical tool for users interested in low delta put selling strategies, making it suitable for both beginners and experienced options traders.

# File Details and Key Functions

## 1. app.py (Updated)
**Purpose:** Main application entry point and UI controller  
dedicated "Low Delta Opportunities" page  
- Set global `MAX_DELTA` constant (0.1)  
- Enhanced paper trading integration  
- Updated navigation menu with new sections  

**Key Functions:**  
- Navigation between different app sections  
- Page rendering for each functional area  
- Session state management for paper trading  

## 2. stock_data.py  
**Purpose:** Stock data retrieval and analysis  
**Key Functions:**  
- `fetch_stock_data(ticker, period)`: Fetches historical price data  
- `get_stock_info(ticker)`: Gets comprehensive stock information  
- `calculate_historical_volatility(ticker, days)`: Calculates annualized volatility  

## 3. option_analysis.py (Updated)  
**Purpose:** Options data retrieval and analysis  
**Key Changes:**  
- Added `get_all_low_delta_puts()` function  
- Enhanced filtering for delta < 0.1  
- Improved risk metrics calculations  

**Key Functions:**  
- `get_option_chain(ticker)`: Fetches all option expiration chains  
- `filter_low_delta_puts(puts_df, max_delta)`: Filters a single expiration  
- `get_all_low_delta_puts(ticker, max_delta)`: Gets low delta puts across all expirations  
- `recommend_put_strategies(ticker, options_data, risk_tolerance)`: Provides recommendations  

## 4. dashboard.py (Updated)  
**Purpose:** Main dashboard and educational content  
**Key Changes:**  
- Added extensive educational content in expandable sections  
- Enhanced metrics for low delta options  
- Added strategy guide and terminology explanations  

**Key Functions:**  
- `create_dashboard(stocks, max_delta)`: Creates the main dashboard view  
- `get_help_content(section)`: Provides context-specific help content  

## 5. paper_trading.py  
**Purpose:** Paper trading simulation  
**Key Functions:**  
- `PaperTradingSimulator` class: Manages paper trading  
  - `sell_put()`: Simulates selling a put option  
  - `close_position()`: Closes an open position  
  - `calculate_pnl()`: Calculates profit/loss  
  - `update_open_positions()`: Updates P&L for all positions  
  - `calculate_put_option_greeks()`: Calculates option greeks  

## 6. portfolio_optimization.py  
**Purpose:** Portfolio construction and optimization  
**Key Functions:**  
- `optimize_put_portfolio()`: Creates an optimized portfolio  
- `display_portfolio_optimization()`: Displays the optimization UI  
- `calculate_correlation_matrix()`: Analyzes stock correlations  
- `calculate_put_portfolio_metrics()`: Calculates portfolio statistics  

## 7. risk_analysis.py  
**Purpose:** Main risk analysis controller  
**Key Functions:**  
- `display_risk_analysis()`: Main risk analysis UI  
- `analyze_option_risk()`: Analyzes risk for a specific option  

## 8. risk_simulation.py  
**Purpose:** Monte Carlo simulations  
**Key Functions:**  
- `run_monte_carlo_simulation()`: Simulates price paths  

## 9. risk_metrics.py  
**Purpose:** Risk metrics calculations  
**Key Functions:**  
- `calculate_put_assignment_probability()`: Estimates assignment probability  
- `calculate_max_loss()`: Calculates maximum potential loss  
- `calculate_value_at_risk()`: Calculates VaR statistics  
- `analyze_portfolio_risk()`: Analyzes risk metrics for a portfolio  

## 10. risk_visualization.py  
**Purpose:** Risk visualization components  
**Key Functions:**  
- `display_risk_metrics()`: Shows risk metrics  
- `display_pnl_chart()`: Creates P&L visualization  
- `display_monte_carlo_simulation()`: Shows simulation results  
- `display_risk_recommendations()`: Provides risk management advice  

## File Interactions  
The files interact in the following way:  
- `app.py` imports and calls functions from all other modules  
- `dashboard.py` uses `stock_data.py` and `option_analysis.py` to populate the dashboard  
- `option_analysis.py` relies on `stock_data.py` to get current prices  
- `portfolio_optimization.py` uses `option_analysis.py` to get options data  
- `risk_analysis.py` coordinates the other risk modules  
- `paper_trading.py` uses `stock_data.py` to get current prices for P&L calculation  
