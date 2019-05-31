# Generating Time Series Data Chart

The time series data stored in TSDB can be filtered by specified parameters and displayed graphically for quick viewing and analysis of data.

## About This Task

This article describes how to configure times series data filtering conditions, generate data charts, and quickly view and analyze data.

## Before You Start

- Storage policies have been configured for device measuring points, and the measuring point data is of numeric type.
- Data has been ingested from devices and stored in TSDB.

## Procedure

1. Log into the EnOS console, select **Time Series Data > Data Insights**, and configure the data filtering conditions.
2. In the **Select Time Range** section, select or specify the time range for querying data. The specific time range represented by each option is as follows:
  - 1H: From 1 hour ago to present moment
  - 1D: From 00:00 of the current day to present moment
  - 7D: From 00:00 of 7 days ago to present moment
  - Customized: Specify the time range for querying data as needed
3. Click the **Select Devices** input box, and select one or more devices for querying data from the pull-down list. The selected devices will be dynamically presented in the **Selected Measuring Points** column for selecting corresponding measuring points. To reselect devices, click **Reset** to clear the list of selected devices.
4. In the **Select Data Type** section, select the type of data you want to view. After selecting different data types, the **Selected Measuring Points** column will dynamically display the corresponding measuring point list.
  - If you select **ALL**, the **Selected Measuring Points** column will display all the measuring points of the selected device accordingly. Moreover, the measuring point data will not be subject to aggregation or state change query.
  - If the **AI** or **PI** type is selected, you also need to select a data aggregation algorithm and aggregation interval applied when querying data. The currently supported aggregators are as follows:
       - count: Taking the number of data points in each time range as the result
       - sum: Taking the sum of the measuring point values in each time range as the result
       - avg: Taking the average of the measuring point values in each time range as the result
       - max: Taking the maximum value of the measuring point values in each time range as the result
       - min: Taking the minimum value of the measuring point values in each time range as the result
       - first: Taking the first measuring point value in each time range as the result
       - last: Taking the last measuring point value in each time range as the result
  - If you select the **DI** type, select whether you need to perform state change query for the device status data.
5. In the **Selected Measuring Points** column, click on the selected device name, expand the list of measuring points, and select one or more measuring points to be queried. The queried measuring point data will be displayed in the chart on the right.


## Result

The queried measuring point data is displayed in the chart on the right. Drag the time line under the chart or use the area zooming tool in the upper right corner of the chart to view detailed information of a specific time range in the chart, including data time stamp, point name, data value, and data curves. See the following example:

.. image:: ../../media/data_chart.png

Under the data chart, you can view the latest data of the selected measuring points and the last updated time of the data. See the following example:

.. image:: ../../media/latest_data.png

Click **Data List** to view the queried data information in a paged table. See the following example:

.. image:: ../../media/data_list.png

## What to Do Next

To view data of other devices or measuring points, select the corresponding device name, data type, and measuring point name for query again.
