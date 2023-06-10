# mlops-hw3
hw3 prefect

# Q1

https://docs.prefect.io/2.10.13/concepts/tasks/?h=task


name -> An optional name for the task. If not provided, the name will be inferred from the function name.

# Q2

Answer: [0 9 3 * *](https://crontab.guru/#0_9_3_*_*)

# Q3

* load data
```bash
mkdir data
wget https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-01.parquet -O data/green_tripdata_2023-01.parquet
wget https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-02.parquet -O data/green_tripdata_2023-02.parquet   
```


* build and deploy run
```bash
prefect project init
prefect deploy orchestrate.py:main_flow -n 'taxi1' -p 'mlops-zoomcamp'
prefect deployment run 'main-flow/taxi1'
```

* start the worker pool
```bash
prefect worker start --pool 'mlops-zoomcamp'
```

logs
```
...
[95]	validation-rmse:5.20087 
[96]	validation-rmse:5.20016
[97]	validation-rmse:5.19983
[98]	validation-rmse:5.19931
[99]	validation-rmse:5.19931
Finished in state Completed()
```

# Q4


```bash
wget https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-03.parquet -O data/green_tripdata_2023-03.parquet
```


logs
```
...
[97]	validation-rmse:5.37512
[98]	validation-rmse:5.37468
[99]	validation-rmse:5.37450
Finished in state Completed()
```

# Q5

https://prefecthq.github.io/prefect-email/#saving-credentials-to-block

`email_send_message -> sends email`


# Q6 

Automation steps `01 Trigger 02 Actions 03 Details`