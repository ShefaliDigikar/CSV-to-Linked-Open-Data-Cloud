# CSV-to-Linked-Open-Data-Cloud
  The LOD Cloud is a Knowledge Graph that manifests as a Semantic Web of Linked Data. It is a diagram which simply represents a collection of interlinked descriptions of entities – objects, events or concepts. It provides a framework for data integration, visualization, unification, and analytics. Linking data sets from multiple sources often creates ambiguity and redundancy in data, but making use of LOD avoids such problems.
</br></br>

### Implementation Details
 The implementation is done using <mark> networkX </mark> library on eCommerce cellphone data. 
 ![image](https://user-images.githubusercontent.com/45465068/98400642-652dad00-208a-11eb-9036-e888cb10f683.png)

 
   1. A LOD cloud is formed using RDF Triples(Subject Predicate Object), so the first step is to preprocess the data into a suitable format.
   
   2. Converting the CSV file into RDF triples. Each product has a unique ID which is chosen as the subject, the attribute name as the predicate, and the specification details for that particular attribute as the object.
  
   3. A LOD cloud consists of nodes and edges. The nodes in the cloud are always unique. Here nodes denote the subject and object present in the triples, whereas the predicate denotes the edges in the graph. 
   
   ![sw1](https://user-images.githubusercontent.com/45465068/98401310-7a570b80-208b-11eb-832b-f2866d0e3dc0.png)

</br>
 
