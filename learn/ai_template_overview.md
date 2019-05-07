# AI Data Aggregation Template

AI (analogy input)  data consists of physical parameters like temperature, pressure, flow, etc. The values of these parameters are collected by various sensors, converted to electric signals by a transmitter, and transferred to the analogy input of the controller.

EnOS streaming processing engine provides a unified AI data aggregation template to process the AI type data ingested from a measure point and assign the processed data to another measure point defined for the same device, thus enabling developers to process real-time AI data easily and quickly.  

## Features

**Rich aggregation algorithm**

Providing rich aggregation algorithms, including `max`, `min`, `avg`, `sum`, and `cnt`.

**Data processing based on time window**

Supporting event-time-based windowing mechanism for AI data aggregation. For detailed information about time window, see [Time Window](../reference/time_window).

**Time window latency setting**

Supporting time window latency. When window latency is set, an intermediate output will be generated (the computed output value of the current window when the next window starts). The intermediate output will be saved in TSDB but will not be archived.

**Invalid data filtering**

Supporting various threshold ranges to filter invalid data. Input data that exceeds the threshold will be processed by the interpolation algorithm.

## Configuring AI Data Aggregation Jobs

Take the following steps to use the Window Aggregation for AI template to quickly create a stream processing job:

1. When initializing the stream processing job, select the **Window Aggregation for AI** template. For detailed information, see [Creating a Stream Processing Job](../howto/stream/creating_job).

2. Configure AI data processing policy. For detailed information, see [Configuring AI Data Aggregation Job](../howto/stream/configuring_ai_template).
