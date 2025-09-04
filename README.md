
# Network_Scans

This repository contains tools for detecting categorical anomalies in network traffic data. Specifically for  features that exhibit only a limited number of values during normal operation, such as Modbus function codes or PLC ports.  
Unexpected new categories (e.g., new ports suddenly appearing) can be an early sign of an intrusion attempt, such as a port scan.

---


## Functions

- **`find_limited_unique_features(df, threshold=10)`**  
  Identify features in a DataFrame that have only a limited number of unique values (aka, categorical features).  
  Useful for detecting categorical features such as ports or Modbus codes.  

- **`compare_limited_unique_features(dict1, dict2)`**  
  Compare two sets of categorical features (e.g., "ports" feature during normal operation  vs. "ports" feature during a time when potential cyber-attacks may be present) and detect when new categories (new unique values) appear.  

- **`generate_plc_dataframe(num_plcs, num_records)`**  
  Generate simulated PLC network data with limited categories (benign) or injected anomalies (e.g., port scans).  

---


## Usage

This project is intended for use with [Jupyter Notebook or JupyterLab](https://jupyter.org/).  
You can also install and launch Jupyter through [Anaconda Navigator](https://www.anaconda.com/download) or another preferred Python distribution.  

Open the included notebook, either through the JupyterLab GUI, or from a terminal:

```bash
jupyter notebook Identifying_Network_Scans.ipynb
```

Follow the examples inside to:  
1. Generate two datasets: normal (df1) and containing attacks (df2).  
2. Compare normal vs. anomalous datasets to detect potential intrusions. 

---

### Example output
```
Alert: New categories detected in feature 'PLC1_inbound_port'.
Original categories: [502, 503, 504]
Current categories: [502, 503, 504, 6001, 7001]
Anomalous categories: [6001, 7001]
```


---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE.txt) file for details.
