# Window Aggregation Template

The value of physical parameters of devices, such as temperature, pressure, flow, etc, can be collected by various sensors, converted to electric signals by a transmitter, and transferred to the input of the controller.

EnOS streaming processing engine provides a unified window aggregation template to process numeric type data that is ingested from a measuring point, and then assigns the processed data to another measuring point defined for the same device. Data developers can use this template to design stream data processing jobs to aggregate real-time device data easily and quickly.  

## Features

**Rich aggregation algorithm**

Providing rich aggregation algorithms, including `max`, `min`, `avg`, `sum`, and `cnt`.

**Data processing based on time window**

Supporting event-time-based windowing mechanism for data aggregation. For detailed information about time window, see [Time Window](../reference/time_window).

**Time window latency setting**

Supporting time window latency. When window latency is set, an intermediate output will be generated (the computed output value of the current window when the next window starts). The intermediate output will be saved in TSDB but will not be archived.

**Invalid data filtering**

Supporting various threshold ranges to filter invalid data. Input data that exceeds the threshold will be processed by the interpolation algorithm.

## Configuring Data Aggregation Jobs

Take the following steps to use the Window Aggregation template to quickly create a stream processing job:

1. When initializing the stream processing job, select the **Window Aggregation** template. For detailed information, see [Creating a Stream Processing Job](../howto/stream/creating_job).

2. Configure the data processing policy. For detailed information, see [Configuring Window Data Aggregation Job](../howto/stream/configuring_ai_template).
