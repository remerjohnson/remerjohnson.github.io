---
layout: post
title: Metadata Experimentation in Jupyter Notebooks
---

Below is just a quick copy and paste from a [jupyter notebook](https://github.com/remerjohnson/rdflib-jupyter/blob/master/transform_metadata_w_rdflib.ipynb) I made last week. It is experimenting with the `rdflib` python library to look at parsing and then serializing RDF into json-ld.  

I really think that stuff like this should be done more in libraries. Not just because it can lead to rapid experimentation and thus new ideas, but because it would immediately let us help students with their notebooks. I know of a few universities that already are on top of this, but this could become a part of the Library Carpentry and other initiatives curricula.    

Anyway, enjoy!

# Transforming metadata with RDFLib

I've been asked to think about how to get our current Research Data Curation projects that exist in our digital collections into various other repositories and aggregators. Some of these are relatively easy to accomplish via "triggers", while others have a richer schema that differs significantly with our ontology.  

This notebook will experiment with ways to utilize the [Python library RDFLib](http://rdflib.readthedocs.io/en/stable/gettingstarted.html) (and a [json-ld extension](https://github.com/RDFLib/rdflib-jsonld) for it) to transform our data into the different target forms. The most common transform would likely be to serialize our data as JSON and/or JSON-LD, then from there some simple transformations of the elements. The first example will be to align with the forthcoming BIOCaddie schema.  

In our actual production environment, since we are a Hydra/Ruby shop, this will likely take place more with the RDF.rb gem, but since I am stronger with Python, it made more sense to play around using that.

Let's first load up the rdflib libraries we'll need:


```python
from rdflib import Graph, plugin
from rdflib.serializer import Serializer
import json
```

## Import the data
For the source data, I am working with data from our staging server, which is locked behind a login. So, the normal way of rdflib parsing a URL will throw 404/file not found errors. Luckily we can save the data from the DAMS as a Turtle (.ttl) file. Then we tell rdflib to parse this graph data as Turtle:


```python
g = Graph().parse("datamares.ttl", format="turtle")
```

## Output (or serialize) the data

RDF data can typically be output, or serialized, in many different formats: RDF/XML, N-Triples, and JSON-LD, to name a few. The list of serializations will depend on the parser of the system you're working with, but rdflib will allow us to serialize the data ourselves. So let's serialize the existing Turtle data into JSON-LD.  

One caveat, though. Our Turtle declares namespaces at the head of the document for all the vocabularies used in the data. JSON-LD will also need that, which it contains within the `context` field. rdflib-jsonld provides guidance on that. Following that we can make the context:


```python
context = {"mads": "http://www.loc.gov/mads/rdf/v1#", "damsid": "http://library.ucsd.edu/ark:/20775/", "owl": "http://www.w3.org/2002/07/owl#", "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#", "dams": "http://library.ucsd.edu/ontology/dams#"}
```

So now we can serialize the data as JSON-LD, by adding the context variable as a parameter:


```python
json_f = g.serialize(format='json-ld', context=context, indent=4)
```


```python
print(str(json_f, 'utf-8'))
```

    {
        "@context": {
            "dams": "http://library.ucsd.edu/ontology/dams#",
            "damsid": "http://library.ucsd.edu/ark:/20775/",
            "mads": "http://www.loc.gov/mads/rdf/v1#",
            "owl": "http://www.w3.org/2002/07/owl#",
            "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#"
        },
        "@graph": [
            {
                "@id": "_:ub3bL7C40",
                "@type": "dams:Copyright",
                "dams:copyrightJurisdiction": "US",
                "dams:copyrightNote": "Constraint(s) on Use: This work is protected by the U.S. Copyright Law (Title 17, U.S.C.). Use of this work beyond that allowed by \"fair use\" requires written permission of the UC Regents. Responsibility for obtaining permissions and any use and distribution of this work rests exclusively with the user and not the UC San Diego Library. Inquiries can be made to the UC San Diego Library program having custody of the work.",
                "dams:copyrightPurposeNote": "Use: This work is available from the UC San Diego Library. This digital copy of the work is intended to support research, teaching, and private study.",
                "dams:copyrightStatus": "Under copyright"
            },
            {
                "@id": "_:ub3bL23C40",
                "@type": "dams:Note",
                "dams:type": "description",
                "rdf:value": "Data collected with acoustic transects inside and outside of Cabo Pulmo National Park. The analysis methods allowed us to estimate the number and size of the fish that were surveyed during the field campaign."
            },
            {
                "@id": "_:ub3bL54C40",
                "@type": "dams:Relationship",
                "dams:personalName": {
                    "@id": "damsid:bd9879500h"
                },
                "dams:role": {
                    "@id": "damsid:bb5086960s"
                }
            },
            {
                "@id": "_:ub3bL62C40",
                "@type": "dams:Relationship",
                "dams:corporateName": {
                    "@id": "damsid:bb27660034"
                },
                "dams:role": {
                    "@id": "damsid:bb3585182w"
                }
            },
            {
                "@id": "_:ub3bL13C40",
                "@type": "dams:Date",
                "dams:beginDate": "2015-03-01",
                "dams:encoding": "w3cdtf",
                "dams:endDate": "2015-03-30",
                "dams:type": "collected",
                "rdf:value": "2015-03-01 to 2015-03-30"
            },
            {
                "@id": "_:ub3bL49C40",
                "@type": "dams:RelatedResource",
                "dams:description": "Finding fish with sound at Cabo Pulmo National Park",
                "dams:type": "related",
                "dams:uri": {
                    "@id": "http://datamares.ucsd.edu/eng/projects/promonitor/finding-fish-with-sound-at-cabo-pulmo-national-park/"
                }
            },
            {
                "@id": "_:ub3bL32C40",
                "@type": "dams:Note",
                "dams:type": "technical details",
                "rdf:value": "Software used: Microsoft Excel and BioSonics acoustic software. Coordinate system: UTM WGS1984."
            },
            {
                "@id": "_:ub3bL66C40",
                "@type": "mads:CorporateName",
                "mads:authoritativeLabel": "UC Regents",
                "mads:elementList": {
                    "@list": [
                        {
                            "@id": "_:ub3bL68C69"
                        }
                    ]
                }
            },
            {
                "@id": "_:ub3bL72C40",
                "@type": "mads:Title",
                "mads:authoritativeLabel": "Acoustic survey of fish in Cabo Pulmo National Park",
                "mads:elementList": {
                    "@list": [
                        {
                            "@id": "_:ub3bL74C69"
                        }
                    ]
                }
            },
            {
                "@id": "_:ub3bL68C69",
                "@type": "mads:FullNameElement",
                "mads:elementValue": "UC Regents"
            },
            {
                "@id": "_:ub3bL36C40",
                "@type": "dams:Note",
                "dams:type": "scope and content",
                "rdf:value": "The data described here have been embargoed until 2016-11-30. Inquiries should be directed to Jack Egerton (osp23e@bangor.ac.uk)"
            },
            {
                "@id": "_:ub3bL74C69",
                "@type": "mads:MainTitleElement",
                "mads:elementValue": "Acoustic survey of fish in Cabo Pulmo National Park"
            },
            {
                "@id": "_:ub3bL40C40",
                "@type": "dams:Note",
                "dams:type": "preferred citation",
                "rdf:value": "Egerton, Jack (20##): Acoustic survey of fish in Cabo Pulmo National Park. In dataMares Project: Fisheries. UC San Diego Library Digital Collections."
            },
            {
                "@id": "_:ub3bL27C40",
                "@type": "dams:Note",
                "dams:displayLabel": "digital object made available by",
                "dams:type": "local attribution",
                "rdf:value": "Research Data Curation Program, UC San Diego, La Jolla, 92093-0175 (http://libraries.ucsd.edu/services/data-curation/)"
            },
            {
                "@id": "_:ub3bL44C40",
                "@type": "dams:Note",
                "dams:type": "methods",
                "rdf:value": "Acoustic survey"
            },
            {
                "@id": "damsid:bd1176351d",
                "@type": "dams:Object",
                "dams:copyright": {
                    "@id": "_:ub3bL7C40"
                },
                "dams:date": {
                    "@id": "_:ub3bL13C40"
                },
                "dams:event": {
                    "@id": "damsid:bd7285620z"
                },
                "dams:geographic": {
                    "@id": "damsid:bd0664401n"
                },
                "dams:language": [
                    {
                        "@id": "damsid:bb87044465"
                    },
                    {
                        "@id": "damsid:bb06839335"
                    }
                ],
                "dams:note": [
                    {
                        "@id": "_:ub3bL40C40"
                    },
                    {
                        "@id": "_:ub3bL32C40"
                    },
                    {
                        "@id": "_:ub3bL44C40"
                    },
                    {
                        "@id": "_:ub3bL36C40"
                    },
                    {
                        "@id": "_:ub3bL27C40"
                    },
                    {
                        "@id": "_:ub3bL23C40"
                    }
                ],
                "dams:provenanceCollectionPart": {
                    "@id": "damsid:bd9606463x"
                },
                "dams:relatedResource": {
                    "@id": "_:ub3bL49C40"
                },
                "dams:relationship": [
                    {
                        "@id": "_:ub3bL62C40"
                    },
                    {
                        "@id": "_:ub3bL58C40"
                    },
                    {
                        "@id": "_:ub3bL54C40"
                    }
                ],
                "dams:rightsHolderCorporate": {
                    "@id": "_:ub3bL66C40"
                },
                "dams:title": {
                    "@id": "_:ub3bL72C40"
                },
                "dams:unit": {
                    "@id": "damsid:bb6827300d"
                }
            },
            {
                "@id": "_:ub3bL58C40",
                "@type": "dams:Relationship",
                "dams:personalName": {
                    "@id": "damsid:bd9879500h"
                },
                "dams:role": {
                    "@id": "damsid:bb1673895k"
                }
            }
        ]
    }


## Interpreting and transforming the data

In addition, we can start to explore and filter the JSON data. We can export the above data as JSON using the `rdflib` command-line tool. For reference, I ran the following:  

`$ rdfpipe -i turtle -o json-ld datamares.ttl > datamares.json`

The cool thing about having data in JSON-LD format is that it is still JSON. This means we can use the many tools that developers use on JSON data. One such tool is `jq`, which can query and transform JSON pretty easily. Let's load the exported json file from above:


```python
DATA="datamares.json"
```

Now we can take a look at everything with the `.` operator from `jq`:


```python
!cat $DATA | jq '.'
```
