# CSV-to-Linked-Open-Data-Cloud
  The LOD Cloud is a Knowledge Graph that manifests as a Semantic Web of Linked Data. It is a diagram which simply represents a collection of interlinked descriptions of entities – objects, events or concepts. It provides a framework for data integration, visualization, unification, and analytics. Linking data sets from multiple sources often creates ambiguity and redundancy in data, but making use of LOD avoids such problems.
</br></br>

### Implementation Details
 The implementation is done on eCommerce data containing details of cellphones. 
 ![image](https://user-images.githubusercontent.com/45465068/98400642-652dad00-208a-11eb-9036-e888cb10f683.png)

 
   1. A LOD cloud is formed using RDF Triples(Subject Predicate Object), so the first step is to preprocess the data into a suitable format.
   ```python
    rdf_data=[]
    strs=''
    for i,j in data.iterrows():
        for k in data.columns:
          strs=str(i)+" "+k+ " "+data.loc[i,k]
          rdf_data.append(strs)
   ```
   2. Converting the CSV file into RDF triples. Each product has a unique ID which is chosen as the subject, the attribute name as the predicate, and the specification details for that particular attribute as the object.
   ```python
   subject=[]
   predicate=[]
   objects=[]
   for i in rdf_data:
     subject.append(i.split(' ')[0])
     predicate.append(i.split(' ')[1])
     objects.append(i.split(' ')[2])
   ```
   3. A LOD cloud consists of nodes and edges. The nodes in the cloud are always unique. Here nodes denote the subject and object present in the triples, whereas the predicate denotes the edges in the graph. 
   ```python
    edges=[]
    plt.figure(figsize =(22, 22)) 
    G=nx.DiGraph()
    pos = nx.spring_layout(G,k=0.20)
    for i in unique_nodes:
      G.add_node(i)

    for (i,j,k) in zip(subject,objects,predicate): 
      edges.append((i,j))
      G.add_edge(i, j, weight=2, title=k,length = 100)

    edge_labels = nx.get_edge_attributes(G, 'title')
    print(edge_labels)
    node_color = [G.degree(v) for v in G] 
    node_size=[G.degree(v)*3000 for v in G] 
    pos = nx.spring_layout(G)
    nx.draw_networkx(G, pos,edge_color='black',width=1,linewidths=1, 
                 with_labels=True,node_size=node_size,node_color=node_color,
                 alpha=0.9,cmap = plt.cm.winter,font_size=16)

    nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels,font_size=16)
    plt.axis('off')
    plt.tight_layout();
    plt.show()
   ```
   ![sw1](https://user-images.githubusercontent.com/45465068/98401310-7a570b80-208b-11eb-832b-f2866d0e3dc0.png)

</br>
 
