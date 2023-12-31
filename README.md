# Google-Cloud-Functions---Cold-Start-Dataset



This dataset was created to simulate the occurrence of cold start in serverless computing. For this, the HealthFaaS framework [1] using a heart disease risk detection scenario is deployed in a serverless environment. To create the dataset, a real working environment was simulated and all requests were sent between 08:00 and 18:00 for 6 days. Triggers for the workload were created using Apache J Meter in HTTP format. The cold start dataset, consisting of 1728 data, contains the information described below.

* DateTime: Shows the time the requests reach the server. It is in dd/mm/yy hh/mm/ss data format.
  
* Hour: Shows the hour of the timestep in DateTime.
  
* Day: Displays the current business day of the DateTime
(1 - Monday, 2- Tuesday, 3- Wednesday, 4- Thursday, 5- Friday, 6- Saturday )

* Latency: It indicates the time it takes for the request sent from the client to return after reaching the server. Therefore, the function includes execution time and cold start time. As a result of the observations, a cold start occurs if there are no requests to the server for more than 15 minutes or if more than 200 simultaneous requests come to the server. (In GCP Cloud Functions, containers are kept warm for up to 15 minutes to prevent cold start [2]. Sudden increases in application load may cause a cold start [3].)
  
* Request: Shows the number of simultaneous requests sent to the Server. It varies between 1 - 250.
  
* CPU Usage: This shows the percentage of RAM usage on the server to respond to the request sent by the client.

* Ram Usage: This shows the percentage of memory usage on the server to respond to the request sent by the client.




Environment Parameters for GCP-Cloud Functions are as follows:


| Name     | Character |
| ---      | ---       |
| Trigger Type | HTTP  |
| RAM     |256Mb     |
| Software Language     | Python 3.11       |
| Region     | Europe - west2b  |


# The Cold Start Dataset

![Dataset_Day_4](https://github.com/MuhammedGolec/Google-Cloud-Functions---Cold-Start-Dataset/assets/61287653/41e047b3-5998-4f7b-93c9-bca3d3533cab)

Figure 1. The Cold Start Dataset for All Variables

![Dataset_Day_4_Latency](https://github.com/MuhammedGolec/Google-Cloud-Functions---Cold-Start-Dataset/assets/61287653/8dd22d57-be4c-422a-9e1c-9e84435051b0)

Figure 2. The Cold Start Dataset as Latency Variable

![Dataset_Day_4_Memory_Usage](https://github.com/MuhammedGolec/Google-Cloud-Functions---Cold-Start-Dataset/assets/61287653/811ffe74-7155-4250-89e2-6049b7e7e775)

Figure 3. The Cold Start Dataset as Memory(RAM) Usage Variable

![Dataset_Day_4_CPU_Usage](https://github.com/MuhammedGolec/Google-Cloud-Functions---Cold-Start-Dataset/assets/61287653/df83f7e1-3a35-496b-a1cd-8da7c0f91482)


Figure 4. The Cold Start Dataset as CPU Usage Variable 

In Figs 1,2,3 and 4, the cold start dataset is shown according to all variables,  memory (RAM) and CPU Usage, respectively.


# Cite this work
This dataset is part of the following publication, please cite when using this dataset:

M. Golec et al., "ATOM: AI-Powered Sustainable Resource Management for Serverless Edge Computing Environments," in IEEE Transactions on Sustainable Computing, doi: 10.1109/TSUSC.2023.3348157.


# References

1- Golec, Muhammed, et al. "HealthFaaS: AI-based Smart Healthcare System for Heart Patients using Serverless Computing." IEEE Internet of Things Journal (2023).

2- Shilkov, Author: Mikhail. “Comparison of Cold Starts in Serverless Functions across AWS, Azure, and GCP.” Mikhail Shilkov, mikhail.io/serverless/coldstarts/big3/. Accessed 9 Oct. 2023. 

3- Shahrad, Mohammad, et al. "Serverless in the wild: Characterizing and optimizing the serverless workload at a large cloud provider." 2020 USENIX annual technical conference (USENIX ATC 20). 2020.


# License
BSD-3-Clause. Copyright (c) 2023, Muhammed Golec. All rights reserved.

See the License file for more details.
 
