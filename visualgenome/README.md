PAPER & CODE & ANALYSIS  

## [VisualGenome](http://visualgenome.org/)  
* image to language  

## [Visual Genome: Connecting Language and Vision Using Crowdsourced Dense Image Annotations](http://visualgenome.org/paper)  
### Abstract  
TO understand the interactions and relationships between objects in an image.  
Each image has an average of 21 objects, 18 attributes, and 18 pairwise relationships between objects.  

### Introduction  
* Comprehensive Scene Understanding: Objects, attributes, relationships and interactions.  
* Three key elements: a grounding of visual concepts to language, a more complete set of descriptions and QAs, and a formalized representation of the components of an image.  

### Visual Genome Data Representation  
Consists of seven main components: region descriptions, objects, attributes, relationships, region graphs, scene graphs, and question answer pairs.  
* computer-generated image region descriptions with bounding boxes.  
* 6 different questions per image: what, where, how, when, who, and why.

### Future Applications  
* Dense image captioning: describe parts of the scene  
* Visual question answering
* Image understanding: evaluation metrics  
* Relationship extraction: also in action recognitin and spatial orientation between objects  
* **Semantic** image retrieval: improve semantic image search  

### Conclusion  
* provide a multi-layer understanding of pictures  
* A large formalized knowledge representation for visual understanding and a more complete set of descriptions and question answers that grouds visual concepts to language.  

## Some revisions to region_visualization_demo  
The original demo was compiled under Python 2.x. If you are using Python 3.x, the following revisions may be helpful.  
* `from StringIO import StringIO` should be revised to `from io import StringIO`. Also, it is optional to add `from io import BytesIO`.  
* Function names. The functions cited in the demo differs from the function defined in `api.py`. Note that certain changes should be made, either to the demo or `api.py`. I strongly suggest read the `api.py` before trying the demo.  
* `print` differs in Python 2.x and Python 3.x. In Python 3.x, if you want to print 'a', you should type `print(a)`.  
* `range` differs in Python 2.x and Python 3.x. To achieve the same function in Python 2.x, you should type `list(range)`.  
* There is a TypeError in the original demo, no matter you compile it with Python 2.x or Python 3.x. You can try to force the variables to be interger, but note only with the variables that you can achieve ideal results.  
* There can be an error which describes you can't use bytes as string. If you have already import `BytesIO`, just change the `StringIO` to `BytesIO`. Of course there are other ways to deal with the error.  

With these changes I successfully complied the demo under Python 3.x. If you have any questions, please feel free to contact me.  

