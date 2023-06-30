# Visualization-of-sensor-Data-in-IoT

## Abstract

The internet of things, or IoT, is a collection of network devices that are connected to sensors. It was getting increasingly difficult to make sense of random data as the number of smart devices connected to sensors increased. Data processing and visualization have been developed since then. For data visualization in IoT, a variety of visualization technologies are available. In this article, we will use Amazon web services to view various sensor data (AWS). AWS offers services such as AWS IoT, which collects sensor data, AWS Kinesis, which processes the raw data, and AWS Quicksight, which displays the data.
Key words: AWS IoT, Sensor Data, Visualization, AWS Quicksight

## Introduction 

The Internet of Things (IoT) has been a trendy topic in recent years. Companies anticipate billions of linked gadgets in the next years. In many aspects, IoT systems differ from traditional software initiatives. Sensor data and a restricted selection of hardware are used to execute applications. For visualization, data from a variety of sensors must be provided in real time with no errors.
In recent years, information and communication has become a major process. The data collected by sensors is useless unless it can be examined. The data collected by wireless sensor networks is often kept in raw format, which is of little use. In this article, we'll look at how data may be utilized to collect information and alert consumers of possible sensor maintenance.

## History 

Data acquired from wireless sensor networks is usually saved and displayed in digital form in the central base station. Many tools are available to assist in the viewing of this vast quantity of material data. However, after reviewing and assessing a number of studies. Most research papers on wireless sensor networks are based on simulation, routing protocol, architecture, data collection, sensor data mining, security issues, and so on, according to the paper, but there are no full-length research papers or documents, nor is there a data visualization tool that focuses on WSNs.

## Problem Definition 

The purpose of this study is to collect data from various sensors and turn it into a more useful form of data using a user interface. To be more exact, make a graph or table out of the digital data. Following that, users may operate devices based on the data displayed by the interface. To do so, we'll start by using AWS services.

## Introduction to AWS services 

AWS is a platform that allows you to accomplish everything online. The Lambda service, Dynamo database service, and IAM service are the three key services we use. The Lambda service is an event listener for data aggregation. Dynamo database service for storing data so you can query it later. In addition, the IAM service may be used to create a role on AWS with extremely limited privileges that is safer to use than your root account. For further information, you won't have to flash your personal or company's main Amazon account's identification or credentials about using the IAM service.
AWS IoT is a managed cloud platform that enables connected devices to interface with cloud applications and other devices in a simple and safe manner. It can also consistently and securely process and route billions of messages to AWS destinations and other devices. There are three other services that assist us in completing this system. The Amazon Kinesis Firehose, Amazon Kinesis Analytics, and Amazon QuickSight services are all available.
Amazon Kinesis Firehose is the simplest way to continually gather, convert, and load streaming data from millions of data sources, such as IoT devices, into AWS. Without having to learn new programming languages or processing frameworks, Amazon Kinesis Analytics allows you to process streaming data from IoT devices in real time with normal SQL, offering actionable insights quickly. The data is sent into Amazon QuickSight once it has been processed. It's a lightning-fast, cloud-based business analytics solution that makes it simple to create visualizations, do ad-hoc research, and swiftly extract business insights from data.


## Dataset

We couldn't get a sensor to connect to AWS and deliver data in real time since we couldn't get it to connect. As a result, we decided to discover a simulator that provides random sampling of data on AWS for data processing. We discovered a software that created random data in real time. The procedure of loading the script into AWS was time-consuming. The dataset comes from GitHub and includes a python script for generating random sensor data. We may also change the script to create a specific sensor dataset. The dataset for this project was gathered by executing a python script on Amazon AWS and utilizing the IAM functionality to create an instance on EC2. This method also allowed us to learn about AWS's capabilities, how networking works in AWS, and how to connect any device with a sensor to AWS.
The python script may be found at the URL below. 
https://github.com/aws-samples/sbs-iot-data-generator/blob/master/sbs.py

##Implementation

Step 1: Creating Instance
 	To begin, we created an AWS account and assigned the IAM role "HCI Project" to it. IAM role is an AWS feature that allows you to grant certain permissions to roles so that anybody having the role's access key may access the account. We built an EC2 instance after creating the role. The Amazon EC2 instance allows us to establish a virtual machine in the cloud for computing.
 
Step 2:  Collect Sensor data 
  On a Linux virtual computer, the instance was generated. Then, in order to store the file locally, we clone the github repository. The status of the instance changed to "Running" after that. The script requires AWS CLI credentials and boto3 to be installed on the system that is running it. We can then use the command line interface to import the file into our AWS account. The.py code was then executed on the EC2 instance and left running until we obtained a large enough dataset of random sensors. 
  
Step 3: Creating Firehose delivery streams
  We used the AWS kinesis firehose function after creating the Dataset. In Amazon Web Services, Firehose is used to store, transform, and load streaming data. We constructed three S3 buckets: one for the source, which pulls raw data from AWS IoT, another for the destination, which outputs device data, and a third for aggregating data from analytics. We utilized a 70-second buffer interval.
 
Step 4:   Receive and forward incoming data
  For AWS Iot, we established a new rule. This rule will be used to reduce the amount of data that has to be processed on AWS Analytics.
 
Step 5 : Process sensor data
  To process the incoming data, we developed a new application in AWS and defined device parameters, device values, Device ID, and timestamps to distinguish each piece of data. We were unable to obtain the results for this step due to technical issues that caused the instance to often disconnect. The incoming data was not detected by the analytics. Step 6 is a suggestion.

Step 6 : Connect the Analytics application 
  We may link the application system to the Analytics interface after the data has been processed. We may pick fast sight for the output of the firehose delivery system that we developed from the console. This is how the outside will seem. 

## Proposed approach and contribution

Sensor data devices produce a massive quantity of data. AWS Analytics can convert the data into a usable format for humans. We can utilize the AWS appsync functionality to link the data to an interface where we can control the device after we've implemented analytics. An application can be built in such a way that both text and speech are allowed to be used. We can create our own interface with a decent dashboard design and enable virtual assistants with speech recognition on a smart phone because AppSync is a premium feature of AWS.

## Conclusion

The purpose was to use Aws to display the sensor data. We loaded, analyzed, processed, and visualized sensor data using AWS features. We can detect trends in the visible data, make predictions, and operate IoT devices with the tips of our fingers. This bridges the gap between human-computer connection, improves living quality, and provides us a glimpse into the future.


## Future Works 
  
According to linked data, each individual is becoming increasingly connected to a growing number of gadgets. A new generation of digital devices will emerge in the future. Simulations that include sensors and track their readings can aid in the prediction of natural disasters. Especially the enormous advantages of data management. Cities can be monitored, protected species can be safeguarded, air quality can be monitored, and natural disasters may be predicted. Predicting future events has more on that. This important future effort will aid in the improvement and monitoring of cities and endangered animals, as well as the air, planes, bridges, and truck fleets, as well as our talks, bodies, and even our dreams.

11.	References
1.	Jung-Sing Jwo,1,2 Ching-Sheng Lin ,1 and Cheng-Hsiung Lee1, “An Interactive Dashboard Using a Virtual Assistant for Visualizing Smart Manufacturing”  Department of Computer Science, Tunghai University, Taichung 40704, Taiwan, Published 3 May 2021.    
2.	Mitiku Wubetie   “IoT Data Visualization With Modern JavaScript Frameworks “ Metropolia University of Applied Sciences , 20 October 2017.  
3.	K. Thorlund, L. Dron, J. Park, G. Hsu, J. I. Forrest, and E. J. Mills, "A real-time dashboard of clinical trials for COVID-19," The Lancet Digital Health, vol. 2, no. 6, pp. e286-e287, 2020.
4.	M. Chen, G. Lampouras, and A. Vlachos, "Sheffield at e2e: structured prediction approaches to end-to-end language generation," E2E NLG Challenge System Descriptions, vol. 85, 2018. 
