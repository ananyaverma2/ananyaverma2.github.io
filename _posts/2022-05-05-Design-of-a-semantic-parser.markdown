---
layout: post
title:  "Design of a semantic parser for knowledge representation using existing computer vision output"
# date:   2022-10-07 18:05:55 +0300
image:  02.jpg
tags:   PROJECT
---

## Motivation 
The main goal of this research is to predict the relationships between two objects in an image and create a queryable knowledge representation, such that given the below image, the model should output the following graph:

### Input
<p align="center" width="100%">
    <img width="55%" src="https://github.com/ananyaverma2/semantic_parser/blob/main/drawings/hammer.png">
</p>

### Output
<p align="center" width="100%">
    <img width="45%" src="https://github.com/ananyaverma2/semantic_parser/blob/main/drawings/hammer_tri.png">
</p>

## Dependencies

The requirements.txt file will list all Python libraries that the code depends on, and they will be installed using:

`pip install -r requirements.txt`

Also, download the pretrained faster-rcnn model from [here](https://drive.google.com/file/d/18n_3V1rywgeADZ3oONO0DsuuS9eMW6sN/view) and place it under faster-rcnn/data/pretrained_models folder.

## Model Architecture
The model uses three features as depicted in the image below to calculate the corresponding scores, that is, visual score, spatial score and semantic score.
1. **Visual features** : They represent the visual attributes of objects in an image and are helpful in finding out the relationships between objects. For example, **man-book** can have many relationships but if we have an image it can be boiled down to just one.
2. **Semantic features** : They represent the subject-object pair. For example, we know that **man-holding-book** is more probable than **man-under-book**. 
3. **Spatial features** : They represent the position of objects in an image and are important in predicting relationships like **on** and **under**.


<p align="left" width="100%">
    <img width="1000" src="https://github.com/ananyaverma2/semantic_parser/blob/main/drawings/main.png">
</p>


Once the above-mentioned features are used to predict the relationships between objects, a knowledge representation is generated from it.

Also, these graphs can be queried using functions :

1. num_of_given_relation(G, predicate):
2. triples_with_given_predicate(G, predicate):
3. is_entity_present(G, entity):

wherein,  G = graph, predicate = relationship, entity = subject/object

#### Use Case:
This use case is created using the graph depicted above
`[input]`
`triples_with_given_predicate(G, "next to")`
`[output]`
`hammer and plas are linked with the relationships next to`
`plas and screwdriver are linked with the relationships next to`

## Prepare Dataset
1. Download the relationships.json file and images [here](http://visualgenome.org/api/v0/api_home.html) and move it to a folder named visual_genome_files.
2. Run dataset.py file by specifying the path of the relationships.json file to the filename. This will generate a json file dataset.json.
3. Update the path of dataset.json in VG_model.py and wherever necessary.

## How to Train

1. Install all the dependencies mentioned above.
2. Run the VG_model.py file to train the model for the desired settings.
3. You can also evaluate the model using the evaluation_model1.py (recall@100 method) and evaluation_method2.py (recall/precision method).

## Visualize the results

1. Once you have the trained model, save it under a folder called models and update its path in demo.py.
2. Now, run demo.py for the single image to visualize the outputs.

## File description

1. dataset.py : takes the relationships.json file from the Visual Genome dataset and extracts the dataset.json file.
2. dataset_loader.py : loads the dataset into the model in VG_model.py file
3. feature_extraction.py : extracts the bounding boxes, labels and RoI features from the faster-rcnn for the image. 
4. visual_features : takes the inputs from feature_extraction.py and returns a visual score.
5. spatial_features.py : return a spatial score.
6. semantic_features.py : return a semantic score.
7. VG_model.py : loads an image, and gets all the three features here to train the model and also calculate the loss of the model.
8. evaluation_method1.py : to evaluate the model using the recall@100 method.
9. evaluation_method2.py : to evaluate the model using the recall method.
10. draw_graph.py : takes the predicted triples as an input and creates a knowledge representation that can be queried.
11. demo.py : visualize the whole model here, give an image as an input and get the knowledge graph for it.


> This repository contains the code whose design is taken from [An Interpretable Model for Scene Graph Generation](https://arxiv.org/pdf/1811.09543.pdf) and [Relationship Proposal Networks](https://openaccess.thecvf.com/content_cvpr_2017/papers/Zhang_Relationship_Proposal_Networks_CVPR_2017_paper.pdf).