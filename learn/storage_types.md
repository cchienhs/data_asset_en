# Storage Types

With the Storage Policy service, EnOS provides a variety of data storage options based on your data storage and data reading requirements. Data is stored by categories (data types and storage time), thus reducing data storage costs and enhancing data reading efficiency.

## Time Series Database (TSDB) Storage

TSDB is suitable for storing important and frequently-accessed data by data types. Data to be stored can be ingested from connected devices or integrated through the Offline Message channel. Asset AI type data, normalized AI type data, DI type data, PI type data, and generic data can be stored separately, and the data storage time can be customized (1 month, 3 months, 6 months, 1 year, and several years). Each type of the stored data can be retrieved by a specific Open API.

For detailed information about TSDB storage, see [Configuring TSDB Storage](../configuring_tsdb_storage).



## Data Archiving

Data Archiving storage is suitable for storing business data of huge size and lower access frequency. The archived files will be synchronized to target database and stored in the specified file path, thus achieving data backup.

For detailed information about data archiving storage, see [Configuring Archive Storage](../howto/archive/configuring_archive_storage).
