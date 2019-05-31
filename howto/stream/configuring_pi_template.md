# Configuring an Electric Power Calculation Job

Use the **Electric Power Calculation** template to quickly create a stream processing job for calculating electric power data uploaded from electric meters. The total electric power data or detailed data in a time interval will be assigned to measuring points in the same model.

## Configuring Calculation Settings

In the **Calculation Settings** section, view and configure the following settings:


1. Currently, the available calculation scope is **Daily**. That is, the cycle for electric power calculation is 1 day. When the electric meter data of the next day arrives, the system will output the total electric power data of the current day.

2. The supported calculation method is **Sum of meter reading delta**. The daily electric power data is equal to the sum of data in all time intervals of the day. For detailed information about the calculation method, see [Electric Power Calculation Logic](../../reference/power_calculation_logic).

3. Select whether you need detailed output of electric power data by fixed intervals.


## Configuring Data Processing Policy

In the **Data Processing** section, click **New Strategy** to configure the data processing policy in the pop-up window. Each data processing policy defines the input point, the output point, the slope threshold, and the scale of the electric meter.

.. note:: The input point, output point, and the model attributes that are bound to the slope threshold and scale must belong to the same model. The input point cannot be the output point.

1. From the **Input Point** drop down list, select the model and measuring point that provides electric meter reading data to be processed. The input point type must be numeral (int, float, or double).

2. From the **Slope Threshold** drop-down list, select a slope threshold policy to filter out the invalid data.

   For example, (0, max] indicates that if the slope of the time interval falls in the range of 0 - max, the electric meter reading data is valid. Invalid data will not be added to the total electric power data. For detailed information about the slope, see [Electric Power Calculation Logic](../../reference/power_calculation_logic).

   You can specify the slope threshold in the following ways:

   - **Fixed threshold**: Enter fixed values for the threshold. The upper and lower limits must be values greater than or equal to 0, and the lower limit must be less than the upper limit.
   - **Bind to model attribute**: Define the threshold with a model attribute. The lower limit is 0 by default, and the upper limit is defined by the model attribute.

3. From the **Scale** drop down list, select a format for the electric meter scale. You can specify the scale in the following ways:

   - **Fixed scale**: Enter a numeric value for the scale.
   - **Bind to model attribute**: Define the scale with a model attribute.

4. From the **Daily Output** field, select a measuring point to store the output of daily electric power data. The type of the output point must be PI.

5. If "Output by Fixed Interval" is enabled, select the corresponding output point and time interval:

   - **Detailed Output**: Select a measuring point to receive the detailed output. The type of the output point must be PI.
   - **Interval**: Select a time interval for the detailed output.

6. Click **OK** to complete the configuration.


## Example

The following example shows the configuration of a typical electric power calculation job:

.. image:: ../../media/pi_stream_sample.png

## Next Steps

[Publishing the Stream Processing Job](publishing_job)
