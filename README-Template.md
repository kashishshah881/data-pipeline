# Dataflow pipeline for wordcount of EDGAR Data  

The aim of the project is to create a data pipeline for scraping and computing the word counts from various lists of EDGAR data.

1. Google Dataflow is used to build the pipeline. 
2. Beautiful soup and Regular expressions are used to scrape and clean the data (i.e remove stopwords, symbols etc) from the EDGAR Website.
3. Apache beam and NLTK tokenizer was used for tokenizing these files.
4. The model was implemented in two phases, one on the local system using default runner,Direct Runner and the other on the google cloud platform using DataFlow runner.
5. The data has been treated as batch data (since apache beam can accomodate both batch and stream data) which was stored in the PCollections and then used Trandform function of teh Apache beam for manipulation. 
6. The words were mapped as negative, positive, litigious, uncertain, strongmodal, weakmodal and constraining using the MCDonald wordlist.
7. These results were then stored into the google storage buckets following the heirachy of the folder structure.


Below is the process flow

<img style="align:center" src="https://drive.google.com/drive/u/2/my-drive">



## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

*  


## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors
Dhruv Panchal,
Kashish Shah,
Manogna Mantripragada


## License

Copyright 2019 Manogna Mantripragada, Kashish Shah and Dhruv Panchal

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Acknowledgments

1. https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3230156
2. https://www.uts.edu.au/sites/default/files/ADG_Cons2015_Loughran%20McDo
nald%20JE%202011.pdf
3. https://drive.google.com/file/d/15UPaF2xJLSVz8DYuphierz67trCxFLcl/view
4.  (https://www.nltk.org/api/nltk.tokenize.html)
5. https://beam.apache.org/get-started/wordcount-example/
