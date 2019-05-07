# Electric Power Calculation Template

In the energy industry, calculation of electric power generation and consumption is very common. EnOS Stream Analytics provides the Electric Power Calculation template to process the electric meter reading data with specific calculation methods and output the total electric power data within a calculation cycle or detailed data by fixed time intervals.

## Features

**Calculation accuracy**

Enhancing electric power calculation accuracy by using the "Sum of delta" calculation method.

**Filtering invalid data**

Invalid electric power data can be filtered out by setting the slope threshold for intervals. For detailed information about the calculation method, see [Electric Power Calculation Logic](../reference/power_calculation_logic).

**Output by fixed interval**

The cycle for electric power calculation is 1 day. Besides, detailed data of fixed intervals can also be generated.

## Configuring Electric Power Calculation Jobs

Take the following steps to use the Electric Power Calculation template to quickly create a stream processing job:

1. When creating the stream processing job, select the **Electric Power Calculation** template. For detailed information, see [Creating a Stream Processing Job](../howto/stream/creating_job).

2. Configure electric power data processing policy. For detailed information, see [Configuring Electric Power Calculation Job](../howto/stream/configuring_pi_template).
