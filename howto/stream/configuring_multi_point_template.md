# Configuring a Multi-Point Data Calculation Job

Use the **Multi-Point Merging** template to quickly create a stream processing job for calculating data of multiple measuring points and assigning the processed data to another measuring point on the same device, by writing customized calculation expressions.

## Setting Triggering Mode

The Multi-Point Merging template currently supports triggering data processing by a measuring point or by fixed frequency.

In the **Triggering Mode** section, set the triggering mode for the stream processing job.

- **Triggering by point**

  From the **Mode** drop down list, select **point**, and then from the **Timing Interpolation** drop down list, select **LastValue**.

  Each time when the data of the triggering point arrives, the data processing task will be triggered. The data time stamp of the triggering point will be used as the time stamp of the output record.

  If the data of a measuring point does not arrive when a data processing task is triggered, the latest data record of the measuring point will be used for calculation. This is how **Timing Interpolation** works.   

- **Triggering by frequency**

  From the **Mode** drop down list, select **frequency**, and then from the **Triggering Frequency** drop down list, select a frequency value.

  The data processing job will be triggered by the specified frequency. The system time of EnOS stream processing engine is used for controlling the trigger.

## Configuring Data Processing Policy

In the **Data Processing** section, click **New Strategy** to configure the data processing policy in the pop-up window.

When the triggering mode is "point", the configuration of a data processing policy record is as follows:

1. From the **Output Point** drop down list, select the measuring point that receives the output value of the data processing expression. Supported data types include int, float, string, and bool (other types will be converted to string).

2. From the **Triggering Point** drop down list, select the measuring point that triggers the data processing strategy.

3. In the **Output Logic** field, type the data processing expression. For supported syntax of the expression, see [Multi-Point Merging Expression Syntax](../../reference/statement_syntax).

4. Click **Check Syntax** to verify the entered data processing expression.

5. Click **OK** to complete the configuration.

   .. note:: The triggering point, output point, and the measuring points and attributes used in the data processing expression must belong to the same model. The triggering point cannot be the output point.

When the triggering mode is "frequency", the configuration of a data processing policy record is as follows:

1. From the **Output Point** drop down list, select the measuring point that receives the output value of the data processing expression. Supported data types include int, float, string, and bool (other types will be converted to string).

2. In the **Output Logic** field, type the data processing expression. For supported syntax of the expression, see [Multi-Point Merging Expression Syntax](../../reference/statement_syntax).

3. Click **Check Syntax** to verify the entered data processing expression.

4. Click **OK** to complete the configuration.

## Example

The following example shows the configuration of a typical multi-point data merging job:

.. image:: ../../media/multi_point_stream_sample.png

## Next Steps

[Publishing the Stream Processing Job](publishing_job)
