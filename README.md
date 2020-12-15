# CSV to Linked Open Data Cloud 
  The LOD Cloud is a Knowledge Graph that simply represents a collection of interlinked descriptions of entities – objects, events or concepts as a Semantic Web of Linked Data. It provides a framework for data integration and visualization. Linking data sets from multiple sources often creates ambiguity and redundancy in data, but making use of LOD avoids such problems.
</br></br>

### Implementation Details
 The implementation is done using  ***networkX*** library on eCommerce cellphone data. 
 ![image](https://user-images.githubusercontent.com/45465068/98400642-652dad00-208a-11eb-9036-e888cb10f683.png)

 
   1. Convert the CSV file into RDF triples(Subject Predicate Object). Product ID is chosen as subject, attribute name as predicate, and specification details as object.
  
   2. The nodes in a LOD cloud are always unique. The nodes denote the subjects and objects in the triples, and the predicate denotes the edges in the graph. 
   ![sw1](https://user-images.githubusercontent.com/45465068/98401310-7a570b80-208b-11eb-832b-f2866d0e3dc0.png)
