## Running Apache JMeter in Docker
This repository provides a guide and a script for running Apache JMeter within a Docker container. This simplifies the process of executing JMeter tests, eliminating the need for complex setup.

## Prerequisites
Before running JMeter in Docker, please ensure that you have the following prerequisites installed:

- **Docker**: Make sure you have Docker engine and Docker Desktop installed.

## Usage(Operating system-Linux)
To run Apache JMeter in Docker, follow these steps:

1.**Download the Script**:Download the script folder from the Git repository.

2.**Prepare Result Folders**: Create two additional folders to store the JMeter results - one for raw results and another for the HTML report.

3.**Execute the Script**: Run the following command to execute the script (modify the paths and script name as needed):

````
docker run --name jmeter \
  -v /path/to/your/script:/jmeter/test \
  -v /path/to/your/results:/jmeter/results \
  -v /path/to/your/html:/jmeter/html \
  -d justb4/jmeter \
  -n -t /jmeter/test/script.jmx \
  -l /jmeter/results/testresults.jtl \
  -e -o /jmeter/html/htmlreport
````
4.**Access the Reports**: You can now access the test reports from your local result folder and the HTML report folder.


5.**View Results in Terminal**: To view the results directly in the terminal, you can use the following step:

  - **Copy Test Results**:Copy the test results from the Docker container to your local folder, use the following command:

````
docker cp jmeter:/jmeter/results/testresults.jtl /path/to/your/results
````
  - **View Results**: Then, use the following command to view the results directly in the terminal
````
cat /path/to/your/results/testresults.jtl
````
Now, you can easily run JMeter tests within a Docker container and access the results with ease.







