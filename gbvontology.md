# Introduction

This ontology defines some concepts used by the GBV library network. The
ontology may include experimental parts.

## Status of this document

The ontology is available in form of this document and:

* in RDF/Turtle: [**`gbvontology.ttl`**](gbv.ttl) 
* in RDF/XML [**`gbv.owl`**](gbvontology.owl)

All forms are generated from a source file written in Pandoc Markdown
syntax.^[Documents are generated using
[makespec](http://jakobib.github.io/makespec/).] Sources and updates are
available at <http://github.com/gbv/gbvontology>.

This is version {VERSION}, last modified at {GIT_REVISION_DATE} with revision
{GIT_REVISION_HASH}.

[Feedback](https://github.com/gbv/gbv/issues) is welcome!

**Revision history**

{GIT_CHANGES}

## Namespaces and ontology

The URI namespace of this ontology is 
[http://purl.org/ontology/gbv#](http://purl.org/ontology/gbv#).
The namespace prefix `gbv` is recommended. The URI of this ontology as a whole
is <http://purl.org/ontology/gbv>.

    @prefix gbv: <http://purl.org/ontology/gbv#> .
    @base        <http://purl.org/ontology/gbv> .

The following namespace prefixes are used to refer to [related ontologies]:

    @prefix cc:   <http://creativecommons.org/ns#> .
    @prefix daia: <http://purl.org/ontology/daia/> .
    @prefix dct:  <http://purl.org/dc/terms/> .
    @prefix dct:  <http://purl.org/dc/terms/> .
    @prefix owl:  <http://www.w3.org/2002/07/owl#> .
    @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
    @prefix skos: <http://www.w3.org/2004/02/skos/core#> .
    @prefix vann: <http://purl.org/vocab/vann/> .
    @prefix voaf: <http://purl.org/vocommons/voaf#> .
    @prefix void: <http://rdfs.org/ns/void#> .
    @prefix vs:   <http://www.w3.org/2003/06/sw-vocab-status/ns#> .
    @prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .

The GBV Ontology is defined in RDF/Turtle as following:

    <> a owl:Ontology, voaf:Vocabulary ;
        dct:title "GBV Ontology" ;
        rdfs:label "GBV" ;
        vann:preferredNamespacePrefix "gbv" ;
        vann:preferredNamespaceUri "http://purl.org/ontology/gbv#" ;
        dct:description "Ontology of common concepts and relationships used in the GBV library network" ;
        dct:modified "{GIT_REVISION_DATE}"^^xsd:date ;
        owl:versionInfo "{VERSION}" ;
        cc:license <http://creativecommons.org/licenses/by/3.0/> ;
        dct:creator "Jakob Voß" .

# Properties

## Datatype properties

###  gvkppn

    gbv:gvkppn a owl:DatatypeProperty ;
        rdfs:label "gvkppn"@en ;
        rdfs:subPropertyOf dct:identifier ;
        rdfs:comment "PPN identifier within the GBV union catalog (GVK)"@en ;
        skos:scopeNote "a PPN in general identifies a record in any PICA database. This property must only be used to identity records in GVK."@en ;
        rdfs:isDefinedBy gbv: .

### iln

    gbv:iln a owl:DatatypeProperty ;
      rdfs:label "iln"@en ;
      rdfs:subPropertyOf dct:identifier ;
      rdfs:comment "internal library number (ILN) as library identifier within the GBV"@en ;
      rdfs:isDefinedBy gbv: .

### eln

    gbv:eln a owl:DatatypeProperty ;
      rdfs:label "eln"@en ;
      rdfs:comment "external library number (ELN) as library identifier within the GBV"@en ;
      rdfs:subPropertyOf dct:identifier ;
      rdfs:isDefinedBy gbv: .


### dbkey

    gbv:dbkey a owl:DatatypeProperty ;
      rdfs:label "dbkey"@en ;
      rdfs:comment "database key, used as prefix in unAPI and at other APIs within the GBV"@en ;
      skos:scopeNote "must comply to the regular expression ^[a-z][a-z0-9-]*[a-z0-9]$"@en ;
      rdfs:subPropertyOf dct:identifier ;
      rdfs:isDefinedBy gbv: .

## Object properties

### opac

    gbv:opac a owl:ObjectProperty ;
       rdfs:label "opac"@en ;
       rdfs:range void:Dataset ;
       rdfs:comment "main catalog of an institution"@en ;
       skos:scopeNote "the main catalog of a library usually contains records about its holdings, but the main catalog could also contain records that are not held by the institution."@en;
       rdfs:domain daia:Institution ;
       rdfs:seeAlso <http://purl.org/cld/terms/catalogueOrIndex> ;
       rdfs:seeAlso <http://id.loc.gov/vocabulary/relators/own> ;
       rdfs:isDefinedBy gbv: .

### srubase

    gbv:srubase a owl:ObjectProperty ;
       rdfs:label "srubase"@en ;
       rdfs:domain void:Dataset ;
       rdfs:comment "SRU interface of a database"@en ;
       rdfs:isDefinedBy gbv: .

### picabase

    gbv:picabase a owl:ObjectProperty ;
       rdfs:label "picabase"@en ;
       rdfs:domain void:Dataset ;
       rdfs:comment "PICA base URL of a database"@en ;
       rdfs:isDefinedBy gbv: .

###  solrbase

    gbv:solrbase a owl:ObjectProperty ;
       rdfs:label "solrbase"@en ;
       rdfs:domain void:Dataset ;
       rdfs:comment "Solr base URL of a database"@en ;
       rdfs:isDefinedBy gbv: .

###  oaibase

    gbv:oaibase a owl:ObjectProperty ;
       rdfs:label "oaibase"@en ;
       rdfs:domain void:Dataset ;
       rdfs:comment "OAI-PMH base URL of a database"@en ;
       rdfs:isDefinedBy gbv: .

## Datatypes

## ppn

    gbv:ppn a rdfs:Datatype ;
       rdfs:label "PPN identifier"@en ;
       rdfs:comment "A PPN in general identifies a record in a PICA database, but it does not indicate which database it comes from."@en ;
       rdfs:isDefinedBy gbv: .


