# Annotated Corpus for Named-Entity Recognition in Medical Case Study Reports
This repository contains manually assigned named-entity annotations of case study reports. The annotations are available for randomly sampled sentences of the BMJ Case Reports journal. Labels are available for the named-entities *age*, *gender*, and *symptom*.  The annotations are assigned by crowdworkers of the Mechanical Turk platform. 



## Annotations

We annotated 90 sentences using two annotation approaches.

- **Sequential:** The sentences are randomly bundled into groups of 3 (i.e., 30 bundles), which are then labeled by the crowdworkers.
- **Groupwise:** The sentences are bundled into groups of 3 based on their semantic similarity. The bundling of semantically similar sentences improves the time-efficiency of the annotation procedure. More information on this approach can be found in the referenced publication.

We refer to the set of the 90 sentences as *small* corpus for which this repository provides the following sets of annotations:

 - **expert-small.json:** annotations by a medical expert
 - **sequential-small.json:** 5 annotations per sentence by crowdworkers using the Sequential approach
 - **groupwise-small.json:** 5 annotations per sentence by crowdworkers using the Groupwise approach

Furthermore, we collect annotations for additional  2,358 sentences (*large* corpus) using the Groupwise approach. Each sentence of the large corpus is labeled by 3 crowdworkers.

## Annotation Format

The annotations are available in the subfolder *data/annotations/*.  The annotations are linked to SentenceIDs. The sentence texts of each SentenceID can be found in *data/sentences.json*. The sentence texts, after being split by whitespace character, are compatible with the named-entity token annotations.

The annotations are in the following JSON-format:  
```  
    "8593c58d9913bc37710dd89aacc3a59d:0:9": [
        {
            "annotation": [
                1,
                0,
                0,
                0,
                0,
                0
            ],
            "wid": 0,
            "type": "gender"
        },
        {
            "annotation": [
                0,
                0,
                0,
                0,
                0,
                0
            ],
            "wid": 0,
            "type": "age"
        },

....   
}
```  
*wid* is a unique worker ID for this set of annotations
*type* is the named-entity type
*annotation* are the token-level annotations assigned to this sentence

## Annotation Interface
The annotation interface used developed for the Mechanical Turk platform is available in the subfolder *annotation_interface*. 

![Screenshot of the annotation interface](https://github.com/Markus-Zlabinger/casereports/annotation_interface/screenshot.jpg)

## Publication  
More details on the Groupwise annotation approach can be found in our publication:
```  
@inproceedings{zlabingerEfficientAnswerAnnotationFrequent2019,
  title = {Efficient {{Answer}}-{{Annotation}} for {{Frequent Questions}}},
  booktitle = {International {{Conference}} of the {{Cross}}-{{Language Evaluation Forum}} for {{European Languages}}},
  author = {Zlabinger, Markus and Rekabsaz, Navid and Zlabinger, Stefan and Hanbury, Allan},
  year = {2019},
  pages = {126--137},
  publisher = {{Springer International Publishing}}
}
```