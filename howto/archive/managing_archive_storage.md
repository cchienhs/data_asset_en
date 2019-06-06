# Managing Data Archiving Policy
When the data archiving policy is configured and submitted, the system will start archiving data immediately as per the configuration. On the **Data Archiving** page, you can view the running status of all the data archiving jobs, and you can also set alarms for the data archiving jobs, view the running logs of the current archiving cycle, edit an archiving policy, or delete an archiving policy.

## Setting Alarms

In case of any exceptions like failure to run an archiving job or data loss during data archiving, the owner of the data archiving policy need to receive an alarm through email or SMS. You can set alarms for a data archiving policy by the following steps:

1. On the **Data Archiving** page, find the submitted data archiving policy in the list of policies.
2. Click **Operations > Alarm Setting** to open the **Alarm Setting** window.
3. Select the **Receiver** of alarms and the **Mode** to send the alarms (Email or SMS).
4. Click **OK** to save the alarm settings.

## Viewing Logs

You can view the running logs of a running data archiving job.

1. On the **Data Archiving** page, find the submitted data archiving policy in the list of policies.
2. Click **Operations > View Log** to open and view the log file.
3. Click **Download Logs** to download and save the log file of the data archiving job.

The log file contains the configuration of the data archiving policy, the archiving job status, the archiving job progress, the number of archived files, and the number of files synchronized to the target storage system.

## Editing Policy

If required by business needs, you can edit and update any submitted data archiving policy.

1. On the **Data Archiving** page, find the submitted data archiving policy in the list of policies.
2. Click the **Edit** icon to open the configuration page of the data archiving policy.
3. Update the data archiving configuration as per business needs.
4. Click **OK** to submit the updated configuration.

The updated data archiving policy will take effect immediately once it is submitted. Any data archiving job that is not completed in the current archiving cycle will automatically run again as per the newly-submitted policy. If all the data archiving jobs in the current archiving cycle have been completed, the updated data archiving policy will take effect in the next archiving cycle. Data of the newly added models will also be archived starting from the next archiving cycle after the updated policy is submitted.

## Deleting Policy

You can delete a data archiving policy by the following steps:

1. On the **Data Archiving** page, find the submitted data archiving policy in the list of policies.
2. Click **Operations > Delete** and confirm to delete the policy.

Once the data archiving policy is deleted, the current archiving jobs will stop immediately. Data been synchronized to the storage system will not be affected. The archived files cached in the platform will be deleted directly and will not be synchronized to the storage system. Archived files that are in the process of synchronization will be synchronized continuously until the synchronization is completed.
