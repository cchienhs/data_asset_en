# Cleaning up Stored Data

EnOS Time Series Data Management supports cleaning up historical data (wrong data, informal data, or useless business data) that is stored in TSDB for releasing storage resource and saving data storage costs. With the Data Cleanup feature, you can delete data of specified models, measuring points, and assets in specified time range. 

.. note:: Deleted data by Data Cleanup jobs cannot be restored. You must ensure that the specified data is eligible to be deleted to avoid risk of data loss.

## About This Task

This article describes how to clean up historical data stored in TSDB and view data cleanup records.

## Before You Start

Determine the model, measuring point, assets, and time range of the data to be deleted.

## Procedure

1. Log in EnOS Console, select **Time Series Data > Data Cleanup**, and complete the data query conditions.

2. **Time**: Select the time range of the data to be deleted (by date and hours).

3. **Model**: Search for and select the model to which the data belongs to.

4. **Point**: Search for and select the measuring point to which the data belongs to.

5. **Asset**: Select one or multiple assets to which the data belongs to.

6. Click the **Clean Up** button, and the system will start deleting data based on the specified conditions.

  .. image:: ../../media/data_cleanup.png

.. note:: Once submitted, the data cleanup job cannot be canceled. Please operate with caution.

## Result

Submitted data cleanup job will be displayed in the **Cleanup Record** table.

1. Check the configuration details and status of the submitted data cleanup job.

   .. image:: ../../media/data_cleanup_status.png

2. Click the **View** icon in the **Operations** column to view the data cleanup details.

   .. image:: ../../media/data_cleanup_details.png

## What to Do Next

To verify the data cleanup result, go to **Time Series Data > Data Insights**, configure the corresponding data query conditions to check if data is cleaned up already.
