
# Annotated Corpus for Named-Entity Recognition in Medical Case Study Reports
This repository contains manually annotated case study reports for the named-entities *age*, *gender*, and *symptom*. The annotations are assigned by crowdworkers of the Mechanical Turk platform. The case study reports were split into sentences before annotation.


## Annotation Format

The 

We release the following sets of annotated :

  
 The datasets contain annotations of 1,147 clinical trial reports with PIC labels and 1,416 clinical trial reports with sentiment labels. The annotations were created by five annotators working as librarians in medical facilities in the UK. Most samples are annotated redundantly by two annotators on average (which allows, e.g., aggregation of labels using majority voting).
 
You find the annotations for sentiment analysis in the subfolder *data/sentiment/*. The annotations for PIC labeling can be found in *data/pic/*. The annotations are linked to sentences, identified by a unique sentence id (senid).  
The senids are in following format **PMID:SENIDX**, describing a PubMedID (PMID) and the index of the sentence (SENIDX). The sentence texts for each senid can be found in *data/sentences.json*. To split a sentence into tokens that align with the named-entities, you can simply split the sentence by whitespace.  
  
The annotations for PIC labeling are in the following JSON-format:  
```  
"7831628:5": {  
"workerid1": [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
"workerid2": [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1 ]
....   
}
```  
The PIC annotations are on a token level by 1 indicating that the token was annotatoed and 0 indicating that the token was not annotated.

The annotations for Sentiment Classification are in the following JSON-format:  
```  
"7831628:5": {  
"workerid1": "negative",
"workerid2": "positive"
....   
}
```  
The sentiment annotations are on a sentence level by differentiating between *positive*, *negative*, and *neutral*.

## Contact Us  
If you have any further questions, please open a new issue in this repository.  
  
## Publication  
More details on the datasets can be found in the following publications:
```  
@inproceedings{zlabinger2018medical,
    title = "Medical Entity Corpus with {PICO} elements and Sentiment Analysis",
    author = "Zlabinger, Markus and Andersson, Linda and Hanbury, Allan and Andersson, Michael and Quasnik, Vanessa and Brassey, Jon",
    booktitle = "Proceedings of the Eleventh International Conference on Language Resources and Evaluation ({LREC} 2018)",
    month = may,
    year = "2018",
    address = "Miyazaki, Japan",
    publisher = "European Language Resources Association (ELRA)",
    url = "https://www.aclweb.org/anthology/L18-1044",
}
```  
  
```  
@article{zlabinger2018extracting,
  title={Extracting the Population, Intervention, Comparison and Sentiment from Randomized Controlled Trials},
  author={Zlabinger, Markus and Andersson, Linda and Brassey, Jon and Hanbury, Allan},
  journal={Studies in Health Technology and Informatics},
  volume={247},
  pages={146--150},
  year={2018}
}
```