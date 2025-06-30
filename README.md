# Forensic-Artifact-Parser-and-Analyzer-for-Custom-Logs
This is a Python-based Command Line Interface (CLI) tool designed for forensic analysis of `.vlog` session logs.

## Features
  * Log Parsing: Parses `.vlog` session logs.
  * Timeline Generation:Generates a structured timeline from log data.
  * Suspicious Activity Detection:Identifies anomalous or suspicious activities (e.g., shadow copy kill + delete events).
  * User Behavior Visualization: Provides visualizations of user activity and detected anomalies.

## Input Log Format
The tool expects log entries in the following format:
```0x1A2B[ts:1719462390]|EVNT:XR-EXEC!@KILL_usr:admin=>C:\Windows\cmd.exe```

## How to Use
1.  Install Dependencies:
    Ensure you have Python installed. Then, install the necessary libraries by running:
    ```bash: pip install -r requirements.txt ```
2.  Place Log Files:
    Place your `.vlog` files into the directory where you intend to run the tool.
3.  Run the CLI Tool:
    Execute the tool from your terminal(powershell). For example:
    ```bash: python cli_tool.py logs/ --timeline --alerts --summary ```

## Output Files
Upon execution, the tool will generate the following output files:
  * `timeline.csv`: Contains valid, structured log entries.
  * `logs.csv`: Stores invalid or corrupted log entries encountered during parsing.
  * `suspected_anomalies.csv`: Lists detected suspicious activities.
  * `*.png`, `*.html`: Visual reports generated from the analysis.

## Visualizations
The tool generates the following visual reports to aid in forensic analysis:
  * `event_frequency.png`: Illustrates event trends over time.
  * `user_activity.png`: Displays activity levels per user.
  * `anomalies_highlighted.png`: Highlights detected suspicious activities within the log data.
