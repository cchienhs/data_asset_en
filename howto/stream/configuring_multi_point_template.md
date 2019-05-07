# Configuring Multi-Point Data Aggregation Job

Use the **Multi-Point Aggregation** template to quickly create a stream processing job for aggregating data of multiple measure points and assigning the processed data to another measure point on the same device, by writing customized calculation expressions.

## Setting Triggering Mode

The Multi-Point Aggregation template currently supports triggering data processing by a measure point or by fixed frequency.

In the **Triggering Mode** section, set the triggering mode for the stream processing job.

- **Triggering by point**

  From the **Mode** drop down list, select **point**, and then from the **Timing Interpolation** drop down list, select **LastValue**.

  Each time when the data of the triggering point arrives, the data processing task will be triggered. The data time stamp of the triggering point will be used as the time stamp of the output record.

  If the data of a measure point does not arrive when a data processing task is triggered, the latest data record of the measure point will be used for calculation. This is how **Timing Interpolation** works.   

- **Triggering by frequency**

  From the **Mode** drop down list, select **frequency**, and then from the **Triggering Frequency** drop down list, select a frequency value.

  The data processing job will be triggered by the specified frequency. The system time of EnOS stream processing engine is used for controlling the trigger.

## Configuring Data Processing Policy

In the **Data Processing** section, click **New Strategy** to configure the data processing policy in the pop-up window.

When the triggering mode is "point", the configuration of a data processing policy record is as follows:

1. From the **Output Point** drop down list, select the measure point that receives the output value of the data processing expression. Supported data types include int, float, string, and bool (other types will be converted to string).

2. From the **Triggering Point** drop down list, select the measure point that triggers the data processing strategy.

3. In the **Output Logic** field, type the data processing expression. For supported syntax of the expression, see [Multi-Point Aggregation Expression Syntax](../../reference/statement_syntax).

4. Click **Check Syntax** to verify the entered data processing expression.

5. Click **OK** to complete the configuration.

   .. note:: The triggering point, output point, and the measure points and attributes used in the data processing expression must belong to the same model. The triggering point cannot be the output point.

When the triggering mode is "frequency", the configuration of a data processing policy record is as follows:

1. From the **Output Point** drop down list, select the measure point that receives the output value of the data processing expression. Supported data types include int, float, string, and bool (other types will be converted to string).

2. In the **Output Logic** field, type the data processing expression. For supported syntax of the expression, see [Multi-Point Aggregation Expression Syntax](../../reference/statement_syntax).

3. Click **Check Syntax** to verify the entered data processing expression.

4. Click **OK** to complete the configuration.

## Example

The following example shows the configuration of a typical multi-point data aggregation job:

.. image:: ../../media/multi_point_stream_sample.png

## Next Steps

[Saving and Publishing Stream Processing Jobs](publishing_job)
