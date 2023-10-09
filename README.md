# Google-Cloud-Functions---Cold-Start-Dataset

# The Cold Start Dataset

This dataset was created to simulate the occurrence of cold start in serverless computing. For this, the HealthFaaS framework [1] using a heart disease risk detection scenario is deployed in a serverless environment. To create the dataset, a real working environment was simulated and all requests were sent between 08:00 and 17:00 for 6 days. Triggers for the workload were created using Apache J Meter in HTTP format. The cold start dataset, consisting of 1204 data, contains the information described below.

* Timestep: Shows the time the requests reach the server. It is in dd/mm/yy data format.

* Request Number: Shows the number of simultaneous requests sent to the Server. It varies between 1 - 1000.

* Latency: It indicates the time it takes for the request sent from the client to return after reaching the server. Therefore, the function includes execution time and cold start time. As a result of the observations, a cold start occurs if there are no requests to the server for more than 15 minutes or if more than 500 simultaneous requests come to the server. (In GCP Cloud Functions, containers are kept warm for up to 15 minutes to prevent cold start [2].)

* Ram Usage: This shows the percentage of memory usage on the server to respond to the request sent by the client.

* CPU Usage: This shows the percentage of RAM usage on the server to respond to the request sent by the client.


Environment Parameters for GCP-Cloud Functions are as follows:

|Trigger Type | HTTP|
|RAM |  256Mb|
|Software Language |  Python 3.11|
|Region |  Europe - west2b|
