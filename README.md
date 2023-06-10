# mlops-hw3
hw3 prefect

# Q1

https://docs.prefect.io/2.10.13/concepts/tasks/?h=task


name -> An optional name for the task. If not provided, the name will be inferred from the function name.

# Q2

Answer: [0 9 3 * *](https://crontab.guru/#0_9_3_*_*)

# Q3

```bash
mkdir data
wget https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-01.parquet -O data/green_tripdata_2023-01.parquet
wget https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-02.parquet -O data/green_tripdata_2023-02.parquet   
```


```bash
prefect project init
prefect deploy orchestrate.py:main_flow -n 'taxi1' -p 'mlops-zoomcamp'