# Configuring a Time Window Data Aggregation Job

Use the **Time Window Aggregation** template to quickly create a stream processing job for aggregating numeric type data of a single measuring point and assigning the processed data to another measuring point on the same device.

## Setting Window Strategy

EnOS stream processing engine uses time window as the data processing mechanism. The configuration of data processing jobs depends on the type of selected time window. Windowing is simply the notion of taking a data source and chopping it up along temporal boundaries into finite chunks for processing (such as sum). In the **Window Strategy** section, configure the time window settings:

1. From the **Window Type** drop down list, select **Tumbling Window** (EnOS stream processing engine currently supports tumbling windows only).
2. From the **Latency Setting** drop down list, select the time for allowing data to arrive late (0 second indicates not processing data that arrive late).

## Configuring Data Processing Policy

In the **Data Processing** section, click **New Strategy** to add an entry of data processing policy. Each processing policy defines the input point, output point, threshold, interpolation, window size, and aggregation method.

1. Click the **Input Point** field and select the model and measuring point that provides input data to be processed. The data type of the measuring point must be numeric.

2. Click the **Threshold** field and specify the method and value to filter the input data. Data exceeding the threshold will be processed by interpolation algorithm.

   .. note:: If the data of the input point is not raw data and the interpolation strategy is "Ignore", the specified threshold will not take effect.

3. Click the **Interpolation** field and select the interpolation algorithm that is used to revise the input data. Currently, interpolation algorithm supports "Ignore" only. Data that exceeds the threshold will not be included in the processing.

4. Click the **Aggregation** field and select the function for computing data in the time window. EnOS streaming processing engine currently supports functions such as `max`, `min`, `avg`, `sum`, and `cnt`.

   - `max`: Compare all valid record values in the time window and output the maximum value.
   - `min`: Compare all valid record values in the time window and output the minimum value.
   - `avg`: Calculate and output the average value of all valid record values in the time window.
   - `sum`: Calculate and output the sum value of all valid record values in the time window.
   - `cnt`: Count all valid record values in the time window and output the total number.

5. Click the **Window Size** field and select a duration value for the time window, which specifies the amount of data to be computed in a single window.

   > In sequential aggregation jobs like "a -> b -> c", the window size of the job "b -> c" should be the same as that of job "a -> b" because "a -> b" will generate an intermediate output.

6. Click the **Output Point** field and select the measuring point to receive the processed results. After the input data is processed, the processed result is transferred to the output point, and an output record is generated. The time stamp of the output record is the start time of the time window.

7. Click the **Save** icon to save the data processing policy.

.. note:: - The output point and the input point must be of the same type.
      - Ensure that the input point and output point belong to the same model.
      - Avoid designing loops in a stream processing job, like a -> b -> c -> a.

## Example

The following example shows the configuration of a typical data aggregation job:

.. image:: ../../media/ai_stream_sample.png

## Managing Data Processing Policy

You can perform the following general operations for data processing policies:

- **Add**: Click **New Strategy** to add a new entry of processing policy. The stream processing job configuration can be saved only when all configuration is completed.
- **Copy**: Click the **Copy** icon to copy an existing policy and configure a new one quickly.
- **Edit**: Each processing policy can be edited if needed.
- **Delete**: Click the **Delete** icon to remove a processing policy if needed.



## Next Steps

[Publishing the Stream Processing Job](publishing_job)
