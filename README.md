# Scraping EDGAR data using Google DataFlow and Buckets


<img src="https://github.com/kashishshah881/data-pipeline/blob/master/img1.jpeg" width="1000">

The main motto of this project is to scrape data using Google Cloud DataFlow and Apache Beam.


### Result:

The **5 Day Rolling Mean of Adjacent Close** has the most effect on the next day adjacent close stock price by **18%**

The Image at the start gives the returns based on **5 Day Rolling Mean of Adjacent Close**



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
pip3 install apache-beam nltk google-cloud-storage
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
> Configure file <a href="https://github.com/kashishshah881/data-pipeline/blob/master/main.py">`main.py`</a> from lines 26 to 29 according to your google credentials. Also enter the bucket location 







Once Everything is installed successfully the below command inside the repository folder

```
python3 main.py
```



## Authors

* **[Kashish Shah](www.kashishshah.com)**


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


