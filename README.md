
#  Light Anomaly Detector

This module detects anomalies in numeric data using the standard deviation method. It's designed as a reusable, lightweight analytics component in Business Intelligence (BI) pipelines for identifying extreme outliers in metric-based data.

---

##  Features

- Automatically detects outliers based on configurable standard deviation thresholds (default: 2σ).
- Visualizes normal vs anomalous data points using `matplotlib`.
- Handles dirty data: converts non-numeric entries to `NaN`, drops invalid rows.
- Easily integrates into existing BI systems or notebooks.

---

##  Example Use Case

Detect revenue spikes, failed login attempts, unusual traffic patterns, or sensor data deviations.

---

##  Project Structure

```
simple_anomaly_detector/
├── anomaly_detector.ipynb        # Jupyter notebook for local testing
├── anomaly_detector.py           # Core detection logic (optional script version)
├── data/
│   └── sample_data.csv           # Example dataset with numeric values
├── README.md                     # This file
├── requirements.txt              # Required packages
```

---


##  How It Works

1. Reads a CSV file from `data/sample_data.csv`.
2. Calculates:
   - Mean (μ)
   - Standard Deviation (σ)
3. Flags as anomaly if:
   ```
   |value - μ| > 2σ
   ```
4. Plots the time series and highlights anomalies in red.

---

##  Example Output

- Blue points = Normal values
- Red points = Anomalies
- Green line = Mean
- Orange lines = ±2σ thresholds

---

##  Requirements

Install the following dependencies:

pip install pandas matplotlib numpy
```


---

##  Customization

- You can change the sensitivity threshold (default is `2` standard deviations):

```python
threshold = 3  # more strict (fewer anomalies)
```

- Replace `sample_data.csv` with any numeric metric dataset (e.g., sales, clicks, latency, etc.).

---

##  Notes

- Ensure the `data/` directory exists.
- The script ignores non-numeric values automatically.
- Ideal for small-to-medium sized BI anomaly checks.

---

##  Feedback

Feel free to open an issue or submit a pull request if you'd like to enhance this module!

---

## 📄 License

MIT License – free to use for personal or commercial projects.
