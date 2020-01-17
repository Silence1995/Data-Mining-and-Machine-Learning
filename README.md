# Data Mining

###### tags: `Data Mining`



## :memo: Homework0

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