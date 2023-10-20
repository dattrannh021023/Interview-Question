# • In a log file with contents as <TIME> : [MESSAGE] : [ERROR_NO] - Human readable text display summary/count of specific error numbers that occurred every hour or a specific hour.

To display a summary or count of specific error numbers that occurred every hour or during a specific hour in a log file, you can use various command-line tools like `grep`, `awk`, and `sort`. Here's an example script that does this:

```bash
#!/bin/bash

# Define the log file path
logfile="/path/to/your/logfile.log"

# Specify the error numbers you want to count (replace with your error numbers)
error_numbers=("ERROR_NO1" "ERROR_NO2" "ERROR_NO3")

# Specify the hour you want to analyze (e.g., "14" for 2 PM)
hour_to_analyze="14"

# Function to extract and count errors for a specific hour
analyze_hourly_errors() {
    hour="$1"
    echo "Summary for Hour $hour:"

    for error_number in "${error_numbers[@]}"; do
        count=$(grep -c "\\[$hour\\]" "$logfile" | grep "\\[$error_number\\]" | wc -l)
        echo "Error $error_number: $count occurrences"
    done
}

# Analyze the specified hour
analyze_hourly_errors "$hour_to_analyze"

```

Replace `/path/to/your/logfile.log` with the actual path to your log file. Modify the `error_numbers` array to include the specific error numbers you want to count. Set the `hour_to_analyze` variable to the hour you're interested in.

This script will search for log entries with the specified error numbers for the specified hour and provide a summary of their occurrences.

You can save this script to a file (e.g., `log_analyzer.sh`), make it executable with `chmod +x log_analyzer.sh`, and then run it to generate summaries for the desired hour. For example:

```bash
./log_analyzer.sh

```

This will display the summary for the specified hour, including the count of each error number.