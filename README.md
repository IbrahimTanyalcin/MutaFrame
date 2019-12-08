


# <img src="https://deogen2.mutaframe.com/logo" alt="mutaframe logo" width="200" height="240" align="center">

> MutaFrame is a single page web app that makes diease predictions on Human Proteome accessible.

## Services

We provide client side ui at mutaframe.com and also several other APIs. When you use our apis, you base uri is always https://deogen2.mutaframe.com/. You need to make a \[GET\] request to receive a response. 

### tools/pseudo?query=

You can search for a gene symbol, accession or a phrase enclosed between quotes, you receive a json response of the information available. MutaFrame only stores refseq sequences, so the closest refseq match to your query is retrieved. etc:

```
GET https://deogen2.mutaframe.com/tools/pseudo?query="breast cancer 2" 

//{"mrna":"NM_000059.3","protein":"NP_000050.2","uniprot":"P51587","name":"BRCA2 DNA repair associated","symbol":"BRCA2"}

GET https://deogen2.mutaframe.com/tools/pseudo?query=TUBA1A

//{"mrna":"NM_001270399.1","protein":"NP_001257328.1","uniprot":"Q71U36","name":"tubulin alpha 1a","symbol":"TUBA1A"}

GET https://deogen2.mutaframe.com/tools/pseudo?query=NM_001130916.2

//{"mrna":"NM_001130916.3","protein":"NP_001124388.1","uniprot":"P36897","name":"transforming growth factor beta receptor 1","symbol":"TGFBR1"}
 
```
### tools/seqfetch?accession=

Provide an accession number and receive back the sequences if the latest refseq version exists. You can provide additional parameters, namely "fields", "response" and "download"

```
GET https://deogen2.mutaframe.com/tools/seqfetch?accession=NM_001130916.2&fields=mrna,protein&response=json

//{"protein":"MEAAVAAP...","mrna":"aaagggccggagcga..."}

GET https://deogen2.mutaframe.com/tools/seqfetch?accession=NM_001130916.2&fields=protein&response=json

//{"protein":"MEAAVAAP..."}

GET https://deogen2.mutaframe.com/tools/seqfetch?accession=NM_001130916.2&fields=protein&response=fasta

//> NM_001130916.2 protein
MEAAVAAPRPRLL...
```

You can trigger a browser side download as well:

```
GET https://deogen2.mutaframe.com/tools/seqfetch?accession=NM_001130916.2&fields=protein&response=json&download=true
```

### tools/orf

ORF (Open Reading Frame) is a sequence finder that relies on "pseudo" and "seqfetch" services. If you want to use the automated retrieved leave the mrna or protein section empty and type your keyword into the other.

Alternatively you can copy paste mrna and protein sequences on their respective lines and click "ANALYZE" to check if the given protein sequence is found within one of the six possible frames of the given mrna.

You can add as many sequences as you like, they will be justified to the left for comparison:

![example tools/orf](https://distreau.com/mutaframe/gifs/mutaframe_orf.gif)





## Bug reports and issues related to MutaFrame

- Describe the issue in a few sentences
- If applicable, write down the UniprotID, if the bug appears in a specific protein
- Provide a screenshot of your console, by right clicking on an empty area and selecting "Inspect".
- Specify if the bug only appears on a certain browser or reproducible accross the board

## Feature request

- Describe the feature you'd like it to be added in a few sentences.
- Provide a link or a simple drawing which depicts feature if possible

## Performance issues

- If you have suggestions for performance increase, take a screen shot of the area where the affected element is located
- If you have performance issues, describe the issue in a few sentences. If possible provide your rig's specs.
- If applicable, specifiy if the performance issue is present across all browsers, or confined to a specific one.

## Supporting 

You can support Mutaframe by:
-  following at [twitter](https://twitter.com/MutaFrame)
- creating an account at mutaframe.com
- helping us create better software by submitting bug reports or feature requests