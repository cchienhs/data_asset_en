# Electric Power Calculation Logic

Electric power calculation is one of the most common calculation scenarios in the energy industry, and the calculation has strict requirements for accuracy. Therefore, processing of abnormal data such as drastic change of electric meter data and abnormal data (like reset of electric meter) is quite important. EnOS stream processing engine integrates abnormal data processing into the calculation process to ensure the accuracy of the electric power data.

## Calculation Method

The Electric Power Calculation template uses the "Sum of delta" calculation method to calculate daily electric power data, with the following steps:

1. Obtain the electric power data of each time interval (delta of electric meter readings in the time interval).
2. Calculate the daily electric power data by summing up the delta in all time intervals of the day. 

The calculation method is illustrated in the following figure:

.. image:: ../media/electric_power_delta.png

- Input: Electric meter readings (`kWh`)
- Time interval: The time range from `t1` through `t2` (Hour)
- Electric power data in the time interval: `Delta(EPower)=kWh2-kWh1`

## Processing of Abnormal Data 

In the chart of electric power data, the slope of the curve in a time interval can be used to filter out abnormal data. Different electric meters allow different slope values. For example, (0, max] indicates that if the slope of a time interval falls in the range of 0 - max, the electric meter reading data of the time interval is valid. Invalid data will not be added to the total electric power data.

The calculation method of the slope is: `slope=Delta(Epower)/Delta(Time)`

.. image:: ../media/electric_power_slope.png

If the slope exceeds a certain range, it may be caused by drastic change of electric meter data or by negative electric power data (an extreme case is that the electric meter reading is reset to zero). This will break the monotonous increasing law of the chart curve. See the following figure:

.. image:: ../media/electric_power_minus_slope.png

## Calculation Logic

Detailed logic for calculating electric power data of different situations is as follows:

### Data changes in a time interval

Check whether the slope of the time interval falls in the threshold `(0,slope_max]`:

- If Yes, add the electric power data of this time interval to the daily value, that is `DailyData=Sum(EPower)*scale`. The system will record the latest electric meter reading data (kWh) and the end time of the interval, which will be used as the starting point for the slope of the next time interval.
- If No, the electric power data of this time interval will not be added to the daily value. The system will also record the latest electric meter reading data (kWh) and the end time of the interval, which will be used as the starting point for the slope of the next time interval.

### Data does not change in a time interval

In the time interval, the electric meter reading does not change. The system does not record the end time of the interval. See the following figure:

.. image:: ../media/electric_power_logic_1.png

As the figure shows, the electric meter reading does not change from t2 through t3. When new data arrives at t4, the time interval for calculation of the slope and electric power data is from t2 through t4.

### Calculation across 0'clock

Generally, the uploaded electric meter reading will be crossing 00:00. As shown in the following figure, this time interval crosses 00:00.

.. image:: ../media/electric_power_logic_2.png

Therefore, the electric power data calculation of the previous day ends at t1, and the data calculation for the current day starts from t1.

## Constant Parameters

In electric power calculation, the following constant parameters are determined by business and devices:

- Electric meter accuracy (digits)
- Slope threshold
- Electric meter scale
- Electric power unit (kWh)

<!--end-->