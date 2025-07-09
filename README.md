

# Stock Signal Smoothing with Kalman Filter and Moving Average

This notebook demonstrates how to smooth stock price data using two common techniques: a Kalman Filter and a simple Moving Average. It compares the effectiveness of these methods in reducing noise from the raw price signal.

## Features

- Fetches intraday stock price data using the `yfinance` library.
- Implements a 1D Kalman Filter for signal denoising.
- Calculates a standard Moving Average for comparison.
- Visualizes the raw price, Kalman filtered price, and moving average.
- Quantifies the smoothing effectiveness using the Signal-to-Noise Ratio (SNR) in decibels (dB).

## Requirements

- Python 3
- Required libraries: `numpy`, `pandas`, `matplotlib`, `filterpy`, `yfinance`

These libraries will be automatically installed when you run the notebook in Google Colab.

## How to Use

1. **Open in Google Colab:** Click the "Open in Colab" badge above.
2. **Run the notebook:** Execute the cells sequentially.
3. **Customize (Optional):** Modify the `fetch_intraday_data` function call to change the stock ticker, interval, or period. You can also adjust the Kalman Filter parameters (`R` and `Q`) and the Moving Average window size.

## Code Description

- **Fetching Data:** The `fetch_intraday_data` function downloads historical stock data using `yfinance`.
- **Kalman Filter:** The `apply_kalman_filter` function implements a 1D Kalman Filter. It models the price as a state with position and velocity and uses the filter to estimate the true state (denoised price) by combining predictions and measurements.
- **Moving Average:** A simple rolling mean is calculated using pandas.
- **Visualization:** `matplotlib` is used to plot the different price series for visual comparison.
- **Signal-to-Noise Ratio (SNR):** The `signal_to_noise_ratio_db` function calculates the SNR. A higher SNR indicates a smoother signal relative to the original data.

## Results

The notebook will output a plot showing the raw price, the Kalman filtered price, and the moving average. It will also print the calculated SNR for both smoothing methods, allowing for a quantitative comparison of their noise reduction capabilities.

## Acknowledgments

- `yfinance` library for providing easy access to stock data.
- `filterpy` library for the Kalman Filter implementation.
