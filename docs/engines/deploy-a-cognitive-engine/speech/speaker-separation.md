# Speech Overview
When you apply artificial intelligence to recordings of human language, it locates, captures, identifies, and categorizes the spoken word quickly, extracting insights previously hidden in unstructured files.

# Speaker Separation Overview
Speaker separation engines distinguish between multiple speakers in audio and video by partitioning recordings and streams into multiple segments according to speaker.

## Use Cases
<details>
  <summary>View More Info</summary>
  
Understand speaker turns in a conversation, for broadcast media, depositions, etc

</details>

## Engine Profile Creation Checklist
<details>
  <summary>View More Info</summary>
  
### Basic Engine Details

( Engine Basics-image goes here)

When creating your engine, it's important to provide details that accurately and describe your engine. The information you enter is what users will see in the Veritone UI when they are selecting engines for processing.
 - **Engine name:** The name of your engine that will be visible through the user interface.
 - **Engine Type:**
	 - **Cognition:** Cognitive engines process data, often using sophisticated algorithms and machine learning techniques, to derive cognitive insights from the data or to transform it for use by another cognitive engine or application. Within the Veritone platform, cognitive engines are assigned into various [classes and categories](https://docs.veritone.com/#/engines/classes/).
	 - **Ingestion:** Ingestion engines are also known as adapters, and we'll often use the term adapter to refer to ingestion engines. Adapters are engines that bring data into the Veritone platform. The data can be in the form of a real-time stream or a bounded file and can be comprised of either structured or unstructured data.
	 - **Aggregator:** Aggregator engines are a new type of engine that we are introducing to assist in processing data in real-time. The role of an aggregator engine is to process the asset fragments that are output by real-time engines.
 - **Engine Category:** *(required)* Select the engine category from the drop-down that matches the type of service your engine will provide. (See [Engine Classes](https://docs.veritone.com/#/engines/classes/) for more information.)
 - **Engine Description:** *(required)* Describe what your engine does in a few sentences. This description displays in various places throughout the user interface where your engine can be viewed.
 - **Library Required:** *(optional)* When run in a special "training" mode, the engine should consume applicable identifier assets from the provided library and, depending on the type of engine, generate a trained model. (See [Library-Enabled-Engines](https://docs.veritone.com/#/libraries/engines) for more information.)
 - **Engine Icon** *(optional)* Upload an icon for your engine from your local file system as a 128x128 png or jpg file.
 - **Engine Logo:** *(required)* Upload a logo image for your engine from your local file system as a 500x250 png or jpg file. The logo is used to identify your engine in the engine selection table of CMS. 

### Deployment Model 

(Deployment Engine- Image goes here)

The deployment model indicates what type of network access your engine requires, after being installed by Veritone, which may affect whether your engine is eligible to run in private and secure servers. You must choose the deployment model that best represents your engine from the following four options:

-   **Network Isolated**: The engine is fully isolated and runs solely within Veritone's infrastructure. It does not require network access.
-   **External Access**: The engine performs its processing within its container and does not send user data off the container. It requires internet access for tasks like license checks and downloading reference data.
-   **External Processing**: The engine performs some or all of its processing outside of Veritone's infrastructure. User data is sent off the container to outside services for processing.
-   **Human Review**: Some or all of the engine’s processing is performed by humans outside of Veritone's infrastructure. (e.g., A human labeling service would fall into this category.)
### Custom Fields (Optional) 
( Custom Fields- Image Goes here)
Depending on the type of your engine, it may require certain parameters to be input by the user in order to process their task. For example a detection based engine may need to know the minimum confidence level for a result to be considered valid. Custom Fields allow you to define these parameters which are then configurable by the end users of your engine. These configured parameters will be available to your engine inside of the payload it receives at runtime.

**Supported Fields:**
 - **Field Name:** Field name will be used as the `key` of the parameter inside of the `taskPayload` given to your engine at runtime.
 - **Field Label:** Field label is used as the friendly name of your parameter when being displayed to end users.
 - **Field Info:** Field info is used to provide description to end users regarding the purpose of the parameter.
 - **Field Type:** Field type represents the type of input your parameter requires. See the table below for details.
 
| Type | Description |
|--|--|
| Text |Standard text input|
| Number |Standard number input with optional min/max/step restrictions|
| Picklist |Define a list of KVP options, where only a single value is selectable|
| MultiPicklist |Define a list of KVP options, where multiple values are selectable|
| SchemaSelection |For engines that accept a data schema as an input|


</details>

## Engine Build Checklist 

<details>
  <summary>View More Info</summary>
	
### 
	
	
</details>
