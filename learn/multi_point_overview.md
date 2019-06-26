# Multi-Point Merging Template

In IoT business scenarios, the data of a measuring point might be calculated from the data of other measuring points of the same device. For example, *point_C = point_A + point_B*. In which, *point_A* and *point_B* are measuring points for ingesting asset raw data. EnOS Stream Analytics provides a Multi-Point Merging template to enable data calculation among multiple measuring points of the same device.

## Features

**Data calculation for multiple points**

Supporting calculation among multiple measuring points of the same device, and associated calculation with master data as well.

**Triggering mode setting**

Data processing can be triggered by the data arrival of a measuring point or by fixed frequency.

**Time series interpolation**

 Supporting time series interpolation strategy (if the data of a measuring point does not arrive when calculation starts, the latest data of the measuring point will be used for calculation).

**Strong syntax for calculation expressions**

Supporting autocomplete of defined models, measuring points, and attributes when writing output logic expressions. For detailed information, see [Multi-Point Merging Expression Syntax](../reference/statement_syntax).

## Configuring Multi-Point Data Calculation Jobs

Take the following steps to use the Multi-Point Merging template to quickly create a stream processing job:

1. When initializing the stream processing job, select the **Multi-Point Merging** template. For detailed information, see [Creating a Stream Processing Job](../howto/stream/creating_job).

2. Configure data processing policy. For detailed information, see [Configuring a Multi-Point Data Calculation Job](../howto/stream/configuring_multi_point_template).
