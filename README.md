## Documentation for New Dataset Management Code Files

This documentation provides comprehensive insights into the functionalities of each code file and instructions on how to use them effectively. This will significantly improve our data management and analysis process, making it more seamless and efficient.

### Data Collection

All dataset management code files are located in the "Data Collection" folder. Below is a detailed overview of each code file and its functionalities:

#### 1. Download_s3_data.ipynb:

**Purpose:**
This notebook facilitates the download of data from our s3 bucket, with the option to use either default AWS credentials or user-provided credentials for environment variable setup.

**Functionality:**
The code empowers users to download data at their preferred frequency and specify the destination path for storage.

**Usage:**
Users can easily uncomment or comment out specific code blocks to download data daily, for a specific date, or within a given date range.

*Day-wise data directory structure:* source_directory/Date/Species/Quality/imagefile

**Example Usage:**
```python
download_path="/content/drive/MyDrive/Dataset/S3 Data/Daily Data"  
data_downloader=S3DataDownloader(bucket_name, download_path)
```

#### 2. Final Data S3.ipynb:

**Purpose:**
This notebook consists of two vital functions, focusing on data organization.

**Functionality:**
The "organize_files" function converts day-wise data obtained from s3 into a species-wise format, ideally suited for ML model training and comprehensive data analysis. Then stored in the Final Data folder.
The "generate_date_list" function generates dates from the specified date till the last date folder in the day-wise dataset.

**Usage:**
To achieve the desired data organization, users simply need to specify the source and destination directories. Users can easily uncomment or comment out specific code blocks to download data daily, or from a specific date.

**Example Usage:**
```python
source_directory ="/content/drive/MyDrive/Dataset/S3 Data/Daily Data"  
destination_directory = '/content/drive/MyDrive/Dataset/Final Data'  
organize_files(source_directory, destination_directory, start_date)
```

#### 3. Manual_data.ipynb:

**Purpose:**
This notebook is designed for handling manual data and converting it to species-wise format.

**Functionality:**
The "copy_manual_data" function copies data from the manual data folder in the source directory to the destination directory.
The "manual_data_to_final_data" function efficiently transforms day-wise data from the source_directory into species-wise data and seamlessly integrates final manual data with s3 final data, resulting in a comprehensive species-wise dataset.

**Usage:**
To successfully execute each function, users only need to provide the necessary source and destination directories.

### Dataset EDA

#### Dataset.ipynb:

**Purpose:**
This notebook is dedicated to visualizing the dataset distribution.

**Functionality:**
The code includes comments explaining each cell's purpose and instructions on how to run them to perform Exploratory Data Analysis (EDA). It automatically generates the Dataset_distribution.xlsx file for reference.

**Usage:**
Users can execute all the cells as per the comments to gain valuable insights into the dataset distribution.

I will ensure that this documentation remains up-to-date with any further changes I make to the code files. If any enhancements or modifications are implemented in the future, I will promptly update the documentation to reflect the latest functionalities.
