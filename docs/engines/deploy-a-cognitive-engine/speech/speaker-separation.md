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


### Step by Step Quick Start Guide
The engine development quick start is divided into seven tutorials that should be completed in order. Because some of the steps require testing and review, the time to complete the steps can vary. However, you can stop at any step in the process and pick up where you left off when you’re ready.

 **1. Create your Engine:** Building an engine in Veritone begins with a few basic steps that define the general details about your technology and give scope to the services it will provide and the internal structures it will support. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-1-create-an-engine)
 
 **2. Construct your Code:** Engines in Veritone are designed with a functional architecture that ensures easy integration to receive tasks, perform work, and return responses. The task processing pipeline follows a logical sequence of actions to fetch the input, retrieve a media asset, process the data, output the results to an asset, and send insights back to Veritone. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-2-construct-code)
 
 **3. Create your Engine Manifest:** Every container uploaded to Veritone for an engine should include a manifest.json file, which contains important information about your engine and build. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-3-manifest)
 
 **4. Package and Upload your Engine Build** When your engine container is created, your manifest file is built, and your code is set, it's time to upload a build. A build is uploaded as a Docker image, which is a package that includes everything needed to run your software, including the code, libraries, environment variables, config files, and manifest file. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-4-upload-build)
 
 **5. Submit a Build for Approval** After your build has passed the compliance testing and is in the _Available_ state, the next step is to submit it to Veritone for review by one of our team members. The review process may take up to a business day to complete. Once reviewed, the build status will change to _Approved_ or _Disapproved_. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-5-submit-build)
 
 **6. Deploy an Engine** Your engine has been built, tested, and approved. Now, with the click of a single button you will make it available to users in the Veritone Platform. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-6-deploy-engine)
 
 **7. Manage an Active Engine or Build** Once your engine has been approved and deployed into the Veritone Platform their are various actions you can take against them. [VIEW MORE](https://docs.veritone.com/#/engines/quick-start/step-7-manage-engine)

### Recommended Manifest Fields

| Field  | Format | Required |  Description
|--|--|--|--|
| engineId | String | Yes| The ID of your engine. You can find your engine ID at the top of the Engines section pages in the Developer Portal. | 
| category | String | Yes| The category of the engine that you are providing. The available options are- avFingerprint- faceDetection- faceRecognition- geolocation- logoRecognition- metadata- objectRecognition- ocr- sentiment- transcription- transcoding- translationRefer to for more information about each engine category. | 
| preferredInputFormat | arrary of strings | Yes| Identify ALL MIME type formats that your engine currently supports as input. If you exclude a file format from this field (even if your engine supports it), your engine may not be selectable when the user ingests a file in that format. The options that Veritone currently supports are listed below: application/json, application/pdf, application/smil+xml, application/ttml+xml, application/x-flv, application/xmlaudio/aac, audio/flac, audio/midi, audio/mp4, audio/mpeg, audio/wav, audio/webmimage/gif, image/jpeg, image/tifftext/csv, text/html, text/plainvideo/3gpp, video/mp4, video/mpeg, video/ogg, video/quicktime, video/webm, video/x-m4v, video/x-ms-wmv, video/x-msvideo . Contact us if you have a MIME type that is not currently supported by Veritone. |
| outputFormats | arrary of strings | Yes| List all of the MIME types of the media formats that your engine will output. The options that Veritone currently supports are listed below:application/json, application/pdf, application/smil+xml, application/ttml+xml, application/x-flv, application/xmlaudio/aac, audio/flac, audio/midi, audio/mp4, audio/mpeg, audio/wav, audio/x-wav, audio/webmimage/gif, image/jpeg, image/tifftext/csv, text/html, text/plainvideo/3gpp, video/mp4, video/mpeg, video/ogg, video/quicktime, video/webm, video/x-m4v, video/x-ms-wmv, video/x-msvideoContact us if you have a MIME type that is not currently supported by Veritone. |
| clusterSize | String | Yes| The cluster size on which your engine should run: small, medium, large (defined below) |


#### Example Manifest

    
    "engineId": "1234567",
    "category": "speaker separation",
    "preferredInputFormat": "audio/wav",
    "outputFormats": ["application/json"],
    "clusterSize": "large",


[View Entire Engine Manifest Here](https://docs.veritone.com/#/engines/manifest)

#### Leveraging Custom Fields
**Use Cases**

### Output Requirements: VTN Standard
#### Schema Field Breakdown
#### JSON Output Example

    { 
    series: [{
    startTimeMs: 0,
    stopTimeMs: 2250,
    speakerId: 'A'
    }, {
    startTimeMs: 2250,
    stopTimeMs: 5050,
    speakerId: 'B'}, {
    startTimeMs: 6000,
    stopTimeMs: 10500,
    speakerId: 'C'
    }, {
    startTimeMs: 12000,
    stopTimeMs: 20000,
    speakerId: 'A'}, 
    {...}, ...]
    }

#### Logging
    

##### Build Modification Implications
    

#### Engine Idling and shut down
    

##### Build Modification Implications
    

#### Creating a “Trainable Engine”
An engine must be configured to be library-enabled. To do so, a field called `libraryRequired` must be set to true on the engine definition. When you create your engine using the VDA "Create engine" wizard, check the "Library Required" option. You can also set this option after engine creation from the Configuration tab on the engine detail page.

##### Use Cases
    
##### Build Modification Implications
    

###### Library Modes
    

-   Toggling it on
    
-   Toggling it off
    

###### Saving the model
    
###### Using an updated model
    
###### Examples & recommendations
    

#### Leveraging the Toolkit (Message Processing Mode Only)
    

##### Value
    
##### Adoption Language
    
##### Roadmap
    
##### Abstractions
    
##### Conditions
    
##### Restrictions
    
##### Walk Through
    
##### Testing With The Toolkit


## Engine Testing Checklist
Before submitting your build, use the following information to test it thoroughly.

### Batch & Legacy Engines
When either a Batch or Legacy engine is deployed to Veritone, a `PAYLOAD_FILE` environment variable is passed to them at runtime which contains the location of the payload file they need to process. The payload file itself contains all of the information the engine needs in order to process the job correctly. In order to test an engine of this type, you will need to simulate an incoming payload to verify your engine can process it successfully. You can get a valid payload to test locally with by following the steps below.
#### Input Example
### Testing Locally 
#### Recommendations 
### Testing on Developer 
#### Generating Input Examples
#### Generating Output Examples
#### Using Ingestion Adapters
### Security Testing: Locally 
	
</details>
