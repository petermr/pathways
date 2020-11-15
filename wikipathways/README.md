# automatic Extraction of Wikipathways

## history

20 random articles from Wikipathways, references supplied by Anders Riutta. I think these were selected by machine learning of pathway images.

PMR downloaded the PDFs from EuropePMC with getpapers. Some downloads failed so they were manually downloaded. One was broken on the EPMC server. The format is ContentMine CProject - basically PDF exploded into named directories.

## evaluation

I assess these on desirability, semantic support, theoretical ease of extraction, and quality of image. The highest scores are retained for experiments. 

After talking with Alex Pico it seems clear that the raw images are not translated automatically into pathways. Several related images are abstracted into a generic pathway, often requiring cell biological semantics. I shall stick with the more molecularly based pathways such as biochemistry.

## examples
### EGF biochemical pathway **
[PMC2259313](PMC2259313/README.md)
### AKT caspase apoptosis **
[PMC2885101](PMC2885101/README.md)
### mindless use of networks
[PMC2966327](PMC2966327/README.md)
### MAPK pathway **
[PMC3683050](PMC3683050/README.md)
### neurodegeneration *
[PMC3794211](PMC3794211/README.md)
### amyloidogenic
[PMC3870290](PMC3870290/README.md)
### retinol *
[PMC4449696](PMC4449696/README.md)
### cancer cell migration
[PMC4503950](PMC4503950/README.md)

## structure and naming

Each PDF is automatically split (by AMI) into images and SVG-text (not included). A PDF can contain many images, but only the pathway/s are recorded here. 

### example
```
PMC2885101/                          # PMC id
├── eupmc_result.json                # download metadata
├── fulltext.pdf                     # PDF
├── fulltext.xml                     # text as JATS-XML (no figures or suppdata)
└── pdfimages
    └── image.6.1.91_505.177_737.    # image page.serial.extent(x1_x2.y1_y2) 
        ├── images.html
        ├── octree                   # colour channels (this example has only shades of gray)
        │   ├── binary.png
        │   ├── channel.000000.png
        │   ├── channel.181818.png
        │   ├── channel.363636.png
...
        │   ├── channel.c7c7c7.png
        │   ├── channel.d8d8d8.png
        │   ├── channel.e9e9e9.png
        │   ├── channel.fefefe.png
        │   ├── channels.html
        │   ├── histogram.svg
        │   └── octree.png
        ├── raw.png                   # image extracted from PDF
        └── raw_o16.png
```

each document now has a README.md with my comments








