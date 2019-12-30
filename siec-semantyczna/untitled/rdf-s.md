# RDF-S



**Declaring Classes of Resources in Turtle**

```text
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>
@base <http://inria.fr/2005/humans.rdfs>
<Woman> a rdfs:Class ; rdfs:subClassOf <Person>, <Female> . 
```

**Declaring Classes of Resources in RDF/XML**

```markup
<rdf:RDF xml:base="http://inria.fr/2005/humans.rdfs" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"> 
  <rdfs:Class rdf:ID="Woman"> 
    <rdfs:subClassOf rdf:resource="#Person"/>
    <rdfs:subClassOf rdf:resource="#Female"/>
  </rdfs:Class>
</rdf:RDF> 
```

**Declaring Types of Properties in Turtle**

```markup
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>
@base <http://inria.fr/2005/humans.rdfs>
<hasMother> a rdf:Property ;  rdfs:subPropertyOf <hasParent> . 
```

**Declaring Types of Properties in RDF/XML**

```markup
<rdf:RDF xml:base="http://inria.fr/2005/humans.rdfs" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"> 
  <rdf:Property rdf:ID="hasMother">
    <rdfs:subPropertyOf rdf:resource="#hasParent"/>
    <rdfs:domain rdf:resource="#Person"/>
    <rdfs:range rdf:resource="#Woman"/>
  </rdf:Property>
</rdf:RDF> 
```

