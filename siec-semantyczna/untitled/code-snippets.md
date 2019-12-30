---
description: Code snippets for RDF
---

# Code Snippets

**An example RDF graph in the N-Triples syntax**

```text
<http://inria.fr/rr/doc.html>  <http://inria.fr/schema#author>  <http://ns.inria.fr/catherine.faron#me> .
<http://inria.fr/rr/doc.html> <http://inria.fr/schema#topic> "Web of Data" .
<http://inria.fr/rr/doc.html> <http://inria.fr/schema#topic> "Semantic Web" .
```

**An Example RDF graph in the Turtle syntax**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>.
@prefix inria: <http://inria.fr/schema#> .
<http://inria.fr/rr/doc.html>  inria:author <http://ns.inria.fr/catherine.faron#me> ;
     inria:topic "Web of Data" , "Semantic Web" .
```

**An example RDF graph in the RDF/XML syntax**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#" >
    <rdf:Description
rdf:about="http://inria.fr/rr/doc.html">
        <inria:author rdf:resource=
"http://ns.inria.fr/catherine.faron#me"/>
        <inria:topic>Web of Data</inria:topic>
        <inria:topic>Semantic Web</inria:topic>
    </rdf:Description>
</rdf:RDF>
```

**Typing Literals with XML Schema Datatypes in the Turtle Syntax**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix inria: <http://inria.fr/schema#> .
<http://inria.fr/rr/doc.html>  inria:date "1995-09-18"^^xsd:date .
```

**Typing Literals with XML Schema Datatypes in the RDF/XML Syntax**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#">
    <rdf:Description rdf:about="http://inria.fr/rr/doc.html">
        <inria:date rdf:datatype="http://www.w3.org/2001/XMLSchema#date">1995-09-18</inria:date>
    </rdf:Description>
</rdf:RDF>
```

**Indicating the Language of Literals in the Turtle Syntax**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix inria: <http://inria.fr/schema#> .
<http://inria.fr/rr/doc.html>  inria:topic "Web of Data"@en , "Web de données"@fr .
```

**Indicating the Language of Literals in the RDF/XML Syntax**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#">
    <rdf:Description rdf:about="http://inria.fr/rr/doc.html">
        <inria:topic xml:lang='en'>Web of Data</inria:topic>
        <inria:topic xml:lang='fr'>Web de données</inria:topic>
    </rdf:Description>
</rdf:RDF>
```

**Typing Resources in the Turtle Syntax**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix inria: <http://inria.fr/schema#> .
<http://ns.inria.fr/catherine.faron#me> a inria:Woman , inria:Researcher .
```

**Typing Resources in the RDF/XML Syntax**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#">
    <inria:Researcher rdf:about="http://ns.inria.fr/catherine.faron#me">
        <rdf:type rdf:resource="http://www.inria.fr/schema#Woman"/>
    </inria:Researcher>
</rdf:RDF>
```

**Describing a Bag of Literals in Turtle**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix inria: <http://inria.fr/schema#> . 
<http://inria.fr/rr/doc.html> inria:author [ a rdf:Bag ;
   rdf:li "Fabien", "Catherine", "Olivier" . ] . 
```

**Describing a Bag of Literals in RDF/XML**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#">
    <rdf:Description rdf:about="http://inria.fr/rr/doc.html">
      
        <inria:author>
          
            <rdf:Bag>
              
                 <rdf:li>Fabien</rdf:li>
                <rdf:li>Catherine</rdf:li>
                
                <rdf:li>Olivier</rdf:li>
                
            </rdf:Bag>
            
        </inria:author>
        
    </rdf:Description>

</rdf:RDF>

```

**Describing a List of Resources in Turtle**

```text
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix inria: <http://inria.fr/schema#> . 
<http://inria.fr/rr/doc.html> inria:author 
    ( <http://ns.inria.fr/fabien.gandon#me> <http://ns.inria.fr/catherine.faron#me>
<http://ns.inria.fr/olivier.corby#me> ) . 
```

**Describing a List of Resources in RDF/XML**

```markup
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:inria="http://inria.fr/schema#">
    <rdf:Description rdf:about="http://inria.fr/rr/doc.html">
      
        <inria:author rdf:parseType="Collection">
            <rdf:Description rdf:about="http://ns.inria.fr/fabien.gandon#me"/>
            
            <rdf:Description rdf:about="http://ns.inria.fr/catherine.faron#me"/>
            
            <rdf:Description rdf:about="http://ns.inria.fr/olivier.corby#me"/>
        </inria:author>
        
    </rdf:Description>

</rdf:RDF>
```

**Named Graphs in TriG**

```markup
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix inria: <http://inria.fr/schema#> .
GRAPH <http://inria.fr/people>
{ 
  <http://inria.fr/rr/doc.html> inria:author. <http://ns.inria.fr/catherine.faron#me> .
}

GRAPH <http://inria.fr/topics>
{ 
  <http://inria.fr/rr/doc.html> inria:topic "Web of Data" .
}
```

**Named Graphs in N-Quads**

```markup
<http://inria.fr/rr/doc.html> <http://inria.fr/schema#author>
   <http://ns.inria.fr/catherine.faron#me> <http://inria.fr/people> . <http://inria.fr/rr/doc.html> <http://inria.fr/schema#topic> 
   "Web of Data" <http://inria.fr/topics> . 
```



