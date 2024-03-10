---
layout: post
title:  "Design of a semantic parser for knowledge representation using existing computer vision output"
# date:   2022-10-07 18:05:55 +0300
image:  semantic_title_image.png
tags:   PROJECT
---

## Motivation 
The main goal of this research is to predict the relationships between two objects in an image and create a queryable knowledge representation, such that given the below image, the model should output the following graph:

### Input
<p align="center" width="100%">
    <img width="55%" src="https://raw.githubusercontent.com/ananyaverma2/images_stored/master/hammer.png">
</p>

### Output
<p align="center" width="100%">
    <img width="45%" src="https://raw.githubusercontent.com/ananyaverma2/images_stored/master/hammer_tri.png">
</p>

## Model Architecture
The model uses three features as depicted in the image below to calculate the corresponding scores, that is, visual score, spatial score and semantic score.
1. **Visual features** : They represent the visual attributes of objects in an image and are helpful in finding out the relationships between objects. For example, **man-book** can have many relationships but if we have an image it can be boiled down to just one.
2. **Semantic features** : They represent the subject-object pair. For example, we know that **man-holding-book** is more probable than **man-under-book**. 
3. **Spatial features** : They represent the position of objects in an image and are important in predicting relationships like **on** and **under**.


<p align="left" width="100%">
    <img width="1000" src="https://raw.githubusercontent.com/ananyaverma2/images_stored/master/main.png">
</p>


Once the above-mentioned features are used to predict the relationships between objects, a knowledge representation is generated from it.

Also, these graphs can be queried using functions :

1. num_of_given_relation(G, predicate):
2. triples_with_given_predicate(G, predicate):
3. is_entity_present(G, entity):

wherein,  G = graph, predicate = relationship, entity = subject/object

#### Use Case:
This use case is created using the graph depicted above: \
`[input]` \
`triples_with_given_predicate(G, "next to")` \
`[output]` \
`hammer and plier are linked with the relationships next to` \
`plier and screwdriver are linked with the relationships next to`



 This repository contains the code whose design is taken from [An Interpretable Model for Scene Graph Generation](https://arxiv.org/pdf/1811.09543.pdf) and [Relationship Proposal Networks](https://openaccess.thecvf.com/content_cvpr_2017/papers/Zhang_Relationship_Proposal_Networks_CVPR_2017_paper.pdf).

 **Github repository:** This work is done in collaboration with Toyota Europe so the code cannot be shared.