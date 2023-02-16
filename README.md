# Exploring the Potential of Machine Translation for Generating Named Entity Datasets: A Case Study between Persian and English [link to paper](https://huggingface.co/Amir13)

Datasets and model are also available in [HuggingFace <g-emoji class="g-emoji" alias="hugs" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f917.png">🤗</g-emoji> ](https://huggingface.co/Amir13)

**Feel free to create a pull request into this repository if you translated any other datasets.**

# Datasets info

Information of English NER benchmarks and translated version of them into Persian

|    **dataset**   	| **train** 	| **dev** 	| **test** 	| **avg** 	|
|:----------------:	|:---------:	|:-------:	|:--------:	|:-------:	|
|   CoNLL2003-en   	|   14041   	|   3250  	|   3453   	|    15   	|
|   CoNLL2003-fa   	|   13746   	|   3159  	|   3380   	|    14   	|
|  $\Delta$ fa-en  	|    -295   	|   -91   	|    -73   	|    -1   	|
| OntoNotes 5.0-en 	|   75187   	|   9603  	|   9479   	|    17   	|
| OntoNotes 5.0-fa 	|   73907   	|   9420  	|   9279   	|    16   	|
|   $\Delta$ fa-en  	|   -1280   	|   -183  	|   -200   	|    -1   	|
|   WNUT 2017-en   	|    3394   	|   1009  	|   1287   	|    18   	|
|   WNUT 2017-fa   	|    3386   	|   1007  	|   1284   	|    17   	|
|  $\Delta$ fa-en  	|     -8    	|    -2   	|    -3    	|    -1   	|
|  NCBI disease-en 	|    5433   	|   924   	|    941   	|    25   	|
|  NCBI disease-fa 	|    5383   	|   916   	|    927   	|    23   	|
|  $\Delta$ fa-en  	|    -50    	|    -8   	|    -14   	|    -2   	|

## Tagsets
```python 
conll2003 = {"O":0, "B-PER":1, "I-PER":2, "B-ORG":3, "I-ORG":4, "B-LOC":5, "I-LOC":6, "B-MISC":7, "I-MISC":8}
```

```python 
wnut2017 ={"O":0, "B-corporation":1, "I-corporation":2 "B-creative-work":3, "I-creative-work":4, "B-group":5,
"I-group":6, "B-location":7, "I-location":8, "B-person":9,
"I-person":10, "B-product":11, "I-product":12,}
```
```python 
ncbi_disease = {"O": 0, "B-dis":1, "I-dis":2}
```
```python 
onenote5 = {"O":0, "B-PERSON":1, "I-PERSON":2, "B-NORP":3, "I-NORP":4, "B-FAC":5, "I-FAC":6, "B-ORG":7, "I-ORG":8, "B-GPE":9, "I-GPE":10, "B-LOC":11, "I-LOC":12, "B-PRODUCT":13, "I-PRODUCT":14, "B-DATE":15, "I-DATE":16, "B-TIME":17, "I-TIME":18, "B-PERCENT":19, "I-PERCENT":20, "B-MONEY":21, "I-MONEY":22, "B-QUANTITY":23, "I-QUANTITY":24, "B-ORDINAL":25, "I-ORDINAL":26, "B-CARDINAL":27, "I-CARDINAL":28, "B-EVENT":29, "I-EVENT":30, "B-WORK_OF_ART":31, "I-WORK_OF_ART":32, "B-LAW":33, "I-LAW":34, "B-LANGUAGE":35, "I-LANGUAGE":36}

```

# Results

Fine-tuned models in both English and Persian are available in [HuggingFace <g-emoji class="g-emoji" alias="hugs" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f917.png">🤗</g-emoji> ](https://huggingface.co/Amir13)
|     **model**    	|    **dataset**   	| **f1** 	|  **p** 	|  **r** 	|
|:----------------:	|:----------------:	|:------:	|:------:	|:------:	|
| xlm-roberta-base 	|   CoNLL2003-en   	|  91.51 	|  90.59 	|  92.45 	|
| xlm-roberta-base 	|   CoNLL2003-fa   	|  85.11 	|  84.49 	|  85.76 	|
|     Pars-Bert    	|   CoNLL2003-fa   	|  84.04 	|  82.07 	|  86.11 	|
|  $\Delta$ fa-en  	|         -        	|  -6.39 	|  -6.09 	|  -6.69 	|
| xlm-roberta-base 	| OntoNotes 5.0-en 	|  89.14 	|  88.62 	|  89.69 	|
| xlm-roberta-base 	| OntoNotes 5.0-fa 	|  83.95 	|  83.96 	|  83.94 	|
|     Pars-Bert    	| OntoNotes 5.0-fa 	|  82.80 	|  82.8  	|  82.82 	|
|  $\Delta$ fa-en  	|         -        	|  -5.2  	|  -4.66 	|  -5.75 	|
| xlm-roberta-base 	|  NCBI disease-en 	|  83.5  	|  83.45 	|  83.54 	|
| xlm-roberta-base 	|  NCBI disease-fa 	|  83.46 	|  81.86 	|  85.13 	|
|     Pars-Bert    	|  NCBI disease-fa 	|  81.71 	|  79.52 	|  84.02 	|
|  $\Delta$ fa-en  	|         -        	|  -0.04 	|  -1.6  	|  1.59  	|
| xlm-roberta-base 	|   WNUT 2017-en   	|  53.0  	|  61.09 	|  46.80 	|
| xlm-roberta-base 	|   WNUT 2017-fa   	|  40.02 	|  44.98 	|  36.05 	|
|     Pars-Bert    	|   WNUT 2017-fa   	|  40.31 	|  48.43 	|  34.52 	|
|  $\Delta$ fa-en  	|         -        	| -12.98 	| -16.11 	| -10.75 	|

# Detailed chrts

## en-fa-conll2003
![](https://github.com/amirsartipi13/Translated-English-Benchmarks-to-Persian/blob/main/charts/fa-conll.png?raw=true)

## en-fa-wnut
![](https://github.com/amirsartipi13/Translated-English-Benchmarks-to-Persian/blob/main/charts/fa-wnut.png?raw=true)

## en-fa-ontonotesv5
![](https://github.com/amirsartipi13/Translated-English-Benchmarks-to-Persian/blob/main/charts/fa-ontonotes.png?raw=true)

# Citation
