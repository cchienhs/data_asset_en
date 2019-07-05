# Querying Metadata of Measuring Points
With the data asset explorer, you can query the metadata information of asset measuring points, including basic information, stream processing lineage, TSDB storage configuration, and instance list.

## Setting Query Conditions
After logging in to EnOS Console, select **Data Asset Explorer** from the left navigation panel. In the **Model / Point** search box, enter keywords to search for models and measuring points. The search results are displayed in the format of {model identifier}::{point identifier}, as shown below:

.. image:: ../../media/metadata_search_result.png

## Viewing Searched Metadata
In the list of searched models and measuring points, click a record to open the details page, and view the following metadata information of the measuring point:

### Basic Information

The basic information of the measuring point metadata includes:

- Identifier
- Name
- Point type

### Stream Processing Lineage

Click the **Stream Processing Lineage** tab to view the stream data processing relationship associated with the measuring point. Click on any node to view the metadata information of the node.

### Storage Policies

Click the **TSDB Storage Config** tab to view the TSDB storage configuration of the measuring point, including the storage policy group, storage type, and storage time for the point data.

.. image:: ../../media/metadata_storage.png

### Instance List

Click the **Instance List** tab to view all the instances associated with the model to which the measuring point belongs. In the **Operations** column, click **Data Quality** or **Data Insights** to view the data quality details and data details for the measuring point of the corresponding instance.

.. image:: ../../media/metadata_devices.png

<!--end-->