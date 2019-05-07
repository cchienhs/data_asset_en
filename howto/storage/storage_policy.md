# Storage Policy Overview

With the Storage Policy service, EnOS provides a variety of data storage options based on your data storage and data reading requirements. Data is stored by categories (data types and storage time), thus reducing data storage costs and enhancing data reading efficiency.

## TSDB Storage Policy
Configure TSDB storage policy to store important and frequently-accessed data separately by data types. TSDB storage policy enables:

**Storage policy groups**

Separate storage policy groups for different projects or domains. For example, data storage policies of the wind power domain and the solar domain can be configured separately. 

**Storage by data types**

Asset AI type raw data, normalized AI type data, DI type data, PI type data, and generic data can be stored separately. Specific APIs can be used to get data stored as different types.

**Multiple data sources**

TSDB can store data that is ingested from connected devices and that is integrated through the offline message channel.

**Customized storage time**

Data storage time can be customized based on your business needs (1 month, 3 months, 6 months, 1 year, and several years).

**Getting data with API**

EnOS provides open APIs for retrieving data stored with different storage policies. When reading data, the APIs can also run specific functions to process the retrieved data, thus improving the data processing efficiency.



<!--

## Archive Storage Policy

Configure archive storage policy to archive business data of huge size and lower access frequency. Archive storage policy enables:

**Archiving specific data**

Archiving data ingested from devices of a specific model or data processed by the stream processing engine

**Setting archived file properties**

Customizing properties of the archived file, including file type, encoding, column delimiter, compression, and file size, which facilitates data analysis and development in the future.

**Specifying archive cycle**

Based on the data amount and business needs, specifying appropriate data archive cycle (1 hour ~ 24 hours). The longer the archive cycle, the more data can be archived, and the number of small files caused by data latency can also be effectively reduced.

**Configuring storage system and path**

Generated archive files will be synchronized to the target storage system and stored under the specified file path.

-->