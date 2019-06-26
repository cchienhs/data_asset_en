# Time Window

When using the Time Window Aggregation template to develop stream processing jobs, you need to configure the window strategy. Detailed introduction to the time window is as follows:

## Event time

In general, event time (time when an event occurs) is used in data aggregation. More precisely, every event has a corresponding time stamp, and the time stamp is part of the data record. Event time is actually a time stamp. When event time is used to define time windows, the stream processing engine can deal with disorderly time flow and variable event time deviation, and compute meaningful results based on the actual time of events.

## Time window

EnOS Stream Processing Engine is based on time windows (micro-batch model) and processes data at the specified window size (interval of batch size). Windowing is simply the notion of taking a data source and chopping it up along temporal boundaries into finite chunks for processing, which determines how often a stream computing task gets the data. EnOS Streaming Processing Engine supports tumbling window.

## Tumbling window

Tumbling windows have a fixed size and do not overlap. Data belonging to a window will be aggregated with the specified method. For example, if you specify a tumbling window with a size of 5 minutes, the current window will be evaluated, and a new window will be started every five minutes. See the example in the following figure.

.. image:: ../media/window_type.png

## Window latency

Generally, when a window closes, the data processing in the window should have been completed, and a new window will be started. However, device data transfer might be delayed because of various factors like device failure and transmission efficiency. Latency setting is introduced to specify the extended validity time of the window after it closes. Late data arriving within the allowed lateness will be added to the window and computed again. Late data arriving after the allowed lateness will be ignored. In the following example, window size is 5 minutes, and *window2* contains data falling in the time range of 11:00 - 11:05. If latency is not enabled, *window2* will be closed at 11:05, and *data1* and *data2* that are arriving late will be ignored. If a latency of 5 minutes is enabled, *data1* will be added to *window2* for computing again, but *data2* will be ignored.

.. image:: ../media/latency_setting.png

<!--end-->
