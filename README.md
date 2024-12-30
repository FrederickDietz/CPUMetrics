Example Usage:


```py
import requests

# URL of the raw file on GitHub
file_url = 'https://raw.githubusercontent.com/FrederickDietz/CPUMetrics/main/CPUMetrics.py'

# Send a GET request to fetch the raw file
response = requests.get(file_url)

# Check if the request was successful
if response.status_code == 200:
    # Save the content to a local file
    with open('CPUMetrics.py', 'wb') as file:
        file.write(response.content)
    print("File downloaded successfully.")
else:
    print("Failed to download the file. Status code:", response.status_code)

from CPUMetrics import *
import random

# Function to calculate IPS (simulated)
def calculate_ips(cpu):
    # Simple simulated calculation of IPS (Instructions per second)
    base_ips = cpu['clock_speed'] * cpu['cores'] * random.uniform(1.5, 3.0)
    return round(base_ips, 2)

# Main function to process CPU data and print capabilities with IPS
def print_cpu_capabilities():
    if not cpus:
        print("No CPUs found.")
        return

    print(f"{'CPU Model':<25} {'Cores':<10} {'Clock Speed (GHz)':<20} {'IPS Metric':<15}")
    print("-" * 70)

    for cpu in cpus:
        model = cpu.get('model', 'Unknown')
        cores = cpu.get('cores', 0)
        clock_speed = cpu.get('clock_speed', 0)
        
        # Calculate IPS metric
        ips = calculate_ips(cpu)
        
        # Print the CPU's details
        print(f"{model:<25} {cores:<10} {clock_speed:<20} {ips:<15}")

if __name__ == "__main__":
    print_cpu_capabilities()
print(len(cpus))
```

Note:
While it isn't possible yet I'd like to get it to a point where it also has the data for what sockets they can fit into, their temperature ranges, power usage, how many were produced etc, but right now that simply isn't possible.










