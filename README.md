# Visualization of Sensor Data in IoT

## Problem Statement
As the number of smart devices connected to sensors grows, making sense of the raw data they produce becomes increasingly difficult. Sensor data is often stored in unstructured formats, making it hard to analyze or visualize. Without proper tools, this data remains underutilized. The goal of this project was to transform raw sensor data into meaningful visual insights using Amazon Web Services (AWS), enabling users to monitor, interpret, and act on IoT data in real time.

## Strategies Tried

### Core Workflow
1. **AWS Setup**: Created an AWS account and assigned an IAM role for secure access.
2. **EC2 Instance**: Launched a Linux-based EC2 instance to simulate sensor data.
3. **Sensor Data Simulation**: Used a Python script from GitHub to generate random sensor data in real time.
4. **Data Streaming**: Configured AWS Kinesis Firehose to collect and buffer incoming data.
5. **Data Routing**: Created AWS IoT rules to filter and forward data efficiently.
6. **Data Processing**: Attempted to process data using AWS Kinesis Analytics (though faced technical issues).
7. **Visualization**: Planned to use AWS QuickSight to visualize processed data.

### AWS Services Used
- **AWS IoT**: Collects and routes sensor data.
- **AWS Lambda**: Listens for events and aggregates data.
- **AWS DynamoDB**: Stores sensor data for querying.
- **AWS Kinesis Firehose**: Streams and buffers data.
- **AWS Kinesis Analytics**: Processes data using SQL.
- **AWS QuickSight**: Visualizes data with dashboards and charts.
- **AWS IAM**: Manages secure access roles.

### Dataset
- Generated using a Python script from [GitHub](https://github.com/aws-samples/sbs-iot-data-generator/blob/master/sbs.py).
- Simulated real-time sensor readings.
- Stored and streamed via AWS services.

## What We Aim to Achieve
- **Real-Time Visualization**: Fully integrate AWS QuickSight for live dashboards.
- **Device Control Interface**: Use AWS AppSync to build a UI for controlling IoT devices.
- **Voice Integration**: Enable voice commands via virtual assistants.
- **Custom Dashboards**: Design user-friendly interfaces for mobile and desktop.
- **Sensor Connectivity**: Connect actual hardware sensors to AWS for real-time data ingestion.

## Observations from the Project
- **AWS Ecosystem is Powerful**: It offers scalable tools for data ingestion, processing, and visualization.
- **Simulated Data is a Good Start**: Using a Python script helped overcome hardware limitations.
- **Technical Challenges Exist**: EC2 instance disconnections and analytics failures hindered full implementation.
- **Security Matters**: IAM roles provided a safer way to manage access without exposing root credentials.

## Recommendations & Improvements
- **Improve Instance Stability**: Ensure EC2 uptime for uninterrupted data flow.
- **Enhance Analytics Integration**: Troubleshoot and refine Kinesis Analytics setup.
- **Use Real Sensors**: Move beyond simulation to connect physical devices.
- **Expand Visualization Tools**: Explore other platforms like Grafana or Power BI.
- **Enable Predictive Insights**: Use machine learning to forecast trends and detect anomalies.
