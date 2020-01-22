# Data Mining

## :memo: Homework_0

##### Dataset: [AirBox Dataset](https://sites.google.com/site/cclljj/dataset-airbox)(We will use ¡§March 2017, Taiwan¡¨ )

### 1. Preprocessing Tasks

- Remove the anomal records. 
  Ex: value of PM2.5 is 0
- Remove the sensors with few data.
- Remove the sensors with few long time gap.

### 2. Data alignment
 
- We require aligned-time data for future works. However, the sensors don¡¦t have a static record time. In order to solve this problem, we can use linear interplolation.
    - Original Data
    
  | time  | 17:04 | 17:18 | 17:22 | 17:29 | 17:36 |
  |-------|-------|-------|-------|-------|-------|
  | pm2.5 | 10    | 20    | 30    | 40    | 50    |
    - New Data
    
  |  time |  17:10 | 17:20 |  17:30 |
  |:-----:|:------:|:-----:|:------:|
  | pm2.5 | 14.286 |   25  | 41.429 | 

### 3. Observation Tasks (Visualization):
    
- Compare different sensors in same time interval.
  ex: Sensor 1 on 8/10 v.s. Sensor 2 on 8/10
- Plot all sensors on the map and describe the dataset.

### 4. Query Tasks:

- How many sensors are there in the dataset?
- Which sensor recorded the highest temperature in March? What¡¦s the temperature? And where's the sensor?
- What were the maximal PM2.5 values of each sensors on 3/5?

### 5. Time Series Data Comparsion Tasks:
- Choose two sensors to do the following steps.
Q: Sequence from Sensor 1
C: Sequence from Sensor 2
Distance(Q, C): Distance between Q & C
    
    1. Offset Translation 
    Q = Q - mean( Q ), C = C - mean( C )
    2. Amplitude Scaling
    Q = (Q - mean( Q )) / std(Q), C = (C - mean( C )) / std( C )
    3. Linear Trend Removal
    Q = detrend( Q ), C = detrend( C )
    4. Noise Removal
    Q = smooth( Q ), C = smooth( C )
    5. Calculate Distance(Q, C) at each step, and compare the difference between original data and transformed data.

## :memo: Homework_1

##### Dataset: same as Homework_0
You can use the dataset before/after preprocessing

### Tasks:
- Define three different transaction, and conduct some experiments on the three mining tasks to find association rules 
- For each task, you should try 
    - Two discretization methods 
        - Divided by 10
        - Divided by 20 
    - Two algorithms 
         - [Apriori](http://rasbt.github.io/mlxtend/user_guide/frequent_patterns/apriori/)
         - [Fp-growth](http://rasbt.github.io/mlxtend/user_guide/frequent_patterns/fpgrowth/) 

- For example, I define a transaction is (pm2.5, humidity, temperature) for device_id=74DA3895C538, then the transaction are (20, 64, 35), (42, 76, 28) ...

### Transactions for each task:

#### Task 1: transaction (PM2.5, humidity, temperature)

| PM2.5 | Humidity | Temperature | 
|:-----:|:--------:|:-----------:|
|  89.0 |   85.0   |    22.12    | 
|  88.0 |   85.0   |    22.12    | 
|  ...  |   ...    |    ...      |
|  90.0	|   86.0   |    21.87    |
#### Task 2: transaction (PM2.5, Humidity , Time)

| PM2.5 | Humidity |   Time   |
|:-----:|:--------:|:--------:|
|  89.0 |   85.0   | 00:00:00 |
|  88.0 |   85.0   | 00:10:00 |
|  ...  |    ...   |    ...   |
|  90.0 |   86.0   | 00:40:00 |
#### Task 3: transaction (PM2.5, PM10, PM1)

| PM2.5 |  PM10 |  PM1 | 
|:-----:|:-----:|:----:|
|  89.0 | 106.0 | 63.0 | 
|  88.0 | 106.0 | 62.0 | 
|  .... | ....  | .... |
|  90.0	| 108.0	| 64.0 |







