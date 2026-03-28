# OICE-LePOS: Old Icelandic Lemmatiser and POS Tagger (SpaCy and UD POS tags version)

## Model Overview

This repository contains a <a href="https://spacy.io/">spaCy</a> (v3.8.11) model  for Part-of-Speech tagging and lemmatization of (normalised) Old Icelandic texts.

Try it out in <a href="https://colab.research.google.com/drive/1V4rqPT1cgULNILu857MCSsrduo_o6eTq?usp=sharing">Google Collab</a>!

The model was trained on all the available MENOTA texts by Andrea de Leeuw van Weenen (AM 132 fol., AM 519 a 4to., and AM 677 4to).

<a href="https://www.menota.org/HB3_ch11.xml">Menota POS-tags</a> were mapped to <a href="https://universaldependencies.org/u/pos/">Universal Dependencies tags</a>, listed here according to their frequency in the training data:

| MENOTA Tag | UD Tag | Notes |
|-----------|--------|-------|
| xVB | VERB | |
| xNC | NOUN | |
| xCU | CCONJ | Can be either CCONJ or SCONJ! |
| xAV | ADV | |
| xAP | ADP | |
| xPE | PRON | |
| xDD | DET | |
| xNP | PROPN | |
| xAJ | ADJ | |
| xRP | PART | |
| xDP | DET | |
| xVP | PART | |
| xCC | CCONJ | |
| xPI | PRON | |
| xIM | PART | |
| xNA | NUM | |
| xCS | SCONJ | |
| xPQ | PRON | |
| xNO | NUM | |
| xUA | — | Rarely used |
| xIT | INTJ | |
| xPA | — | Occurs < 30 times |
| xEX | — | Occurs once |


Notes: 

- <b>xCU</b> is defined in MENOTA guidelines as "used if the encoder (in rather unusual cases) cannot decide whether a word is a conjunction or a subjunction" (Ch. 11, 11.5.11). It can be mapped either to CCONJ or SCONJ in UDP. For this model, it is mapped to CCONJ, but users should be aware of this ambiguity when using the model.

- Model currently under evaluation for out-of-domain performance.

- I could not run the model in Windows, only in Linux environments. I have not tested it on MacOS.

WIP: 

- Training for more granular tags.

## Model Details
- **Model ID:** `OICE-LePOS-spaCy-UD`
- **Language:** Old Icelandic (non)
- **Task:** Token Classification (POS tagging, Lemmatization)
- **Base Model:** None

## Intended Use
- Academic research in historical linguistics
- Old Icelandic text processing and text analysis

## Training Data

- Corpus size: 397668 word tokens across 27067 text chunks of differing lengths. 

- Training-validation-test split: 80-10-10.

- Sources: <a href="https://clarino.uib.no/menota/catalogue/menota">AM 132 fol., AM 519 a 4to, and AM 677 4to</a>, edited and annotated by Andrea de Leeuw van Weenen.

## Training

See [training notebook](notebooks/OICE_LePOS_Training.ipynb) for details. 

## Performance Metrics
| Category | Accuracy (spaCy) | Macro F1-Score (sklearn) |
|--------|-------|-------|
| POS | 0.96  | 0.87  |
| Lemma | 0.93  | 0.58  |

See [evaluation notebook](notebooks/OICE_LePOS_Eval.ipynb) for a more detailed breakdown of performance. 

A more detailed evaluation performance and comparison with other models is currently underway.


## Usage
TODO

Try it out in <a href="https://colab.research.google.com/drive/1V4rqPT1cgULNILu857MCSsrduo_o6eTq?usp=sharing">Google Collab</a>!

See [usage notebook](notebooks/OICE_LePOS_Examples.ipynb) for examples (you will likely have to change the path to the model).

## Limitations
- Works on text normalised similarly to de Leeuw van Weenen's normalisation of the MENOTA texts.
- Out-of-domain performance is currently under evaluation.
- Works only in Linux environments (?)

<!--## Citation
```bibtex
@misc{model_citation,
    author={NKCZ},
    title={OICE-LePOS: Old Icelandic Lemmatiser and POS Tagger},
    year={2026}
}
```
-->