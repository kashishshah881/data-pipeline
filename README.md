# Scraping EDGAR data using Google DataFlow and Buckets


<img src="https://github.com/kashishshah881/data-pipeline/blob/master/img1.jpeg" width="1000">


The aim of the project is to create a data pipeline for scraping and computing the word counts from various lists of EDGAR data.

1. Google Dataflow is used to build the pipeline. 
2. Beautiful soup and Regular expressions are used to scrape and clean the data (i.e remove stopwords, symbols etc) from the EDGAR Website.
3. Apache beam and NLTK tokenizer was used for tokenizing these files.
4. The model was implemented in two phases, one on the local system using default runner,Direct Runner and the other on the google cloud platform using DataFlow runner.
5. The data has been treated as batch data (since apache beam can accomodate both batch and stream data) which was stored in the PCollections and then used Trandform function of teh Apache beam for manipulation. 
6. The words were mapped as negative, positive, litigious, uncertain, strongmodal, weakmodal and constraining using the MCDonald wordlist. The list can be found <a href='https://drive.google.com/file/d/15UPaF2xJLSVz8DYuphierz67trCxFLcl/view?usp=sharing'>Here</a>
7. These results were then stored into the google storage buckets following the heirachy of the folder structure.


Below is the process flow

<img src="https://github.com/kashishshah881/data-pipeline/blob/master/img2.png" width="300" position='center'>

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

```
git clone https://github.com/kashishshah881/data-pipeline.git

```

### Prerequisites

What things you need to install the software:

```
Python3.5+
Apache Beam
Google Cloud Storage
NLTK
```

### Installing

Run These Commands on the terminal
```
pip3 install apache-beam nltk google-cloud-storage apache-beam[gcp]
```

### Setup For Running in Google Cloud DataFlow
##### Step 1
You need to setup Google Cloud Storage Buckets. Goto cloud.google.com and create a bucket. 
Create 2 folders inside the bucket `temp` and `staging` for creating a temperory and staging location for apache beam to interact with.
##### Step 2
Test If you have adequate access writes to your Bucket by running the example shown <a href='https://googleapis.dev/python/storage/latest/index.html#example-usage'>Here</a>
##### Step 3
Spin up a Google VM Instance <a href='https://console.cloud.google.com/compute/instances'> Here </a> with minimum configuration since DataFlow is a managed service, it handles the resources part.
##### Step 4
> Configure file <a href="https://github.com/kashishshah881/data-pipeline/blob/master/main.py">`main.py`</a> from lines 26 to 29 according to your google credentials. Also enter the bucket location in lines 324 to 331 in <a href="https://github.com/kashishshah881/data-pipeline/blob/master/main.py">`main.py`</a>
##### Step 5
Once Everything is installed successfully the below command inside the repository folder
```
python3 main.py
```



## Authors

* **[Kashish Shah](http://www.kashishshah.com)**
* **[Dhruv Panchal](www.linkedin.com/in/panchaldhruv)**
* **[Manogna Mantripragada](www.linkedin.com/in/manogna-mantripragada)**



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


