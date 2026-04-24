
***

# A Stratified Part-of-Speech Tagging Dataset of the *Beiyou shi*

## Introduction
This repository provides a comprehensive part-of-speech (PoS) tagging dataset for the *Beiyou shi* (北遊詩) by Chushi Fanqi (楚石梵琦). [cite_start]The analytical corpus comprises 322 poems, all of which are derived from a meticulously curated and clean **TEI-encoded critical edition** of the text[cite: 51]. This foundational TEI edition is available at: [https://github.com/xiangbuddha/-TEI--Beiyou-shi-TEI](https://github.com/xiangbuddha/-TEI--Beiyou-shi-TEI). [cite_start]The primary objective of this project is to provide a structured, reproducible linguistic profile of this collection, anchored in its digital philological source[cite: 51, 54].

## Methodology and Tagging Workflow
[cite_start]The dataset was constructed using a three-layer tagging framework to ensure high accuracy and stability in processing Classical Chinese poetic language[cite: 108].

1.  [cite_start]**Initial Processing**: Word segmentation and tagging were initially performed using HanLP’s multi-task model for Classical Chinese, which generated two sets of raw labels: Universal PoS (UPOS) and PKU-style tags[cite: 92, 93].
2.  [cite_start]**Lexicon-based Correction**: A domain-specific lexicon (containing Buddhist terminology and proper nouns) and a correction table derived from a manual audit of the text were applied to override recurring model errors[cite: 101, 104].
3.  [cite_start]**Dynamic Adjudication**: I implemented an adjudication procedure where UPOS and PKU tags served as complementary inputs[cite: 109]. [cite_start]Conflicts were resolved through fixed priority rules—such as preserving PKU-style temporal and locative distinctions—and local contextual evidence to determine the final analytical tag for each token[cite: 115, 116, 117].

## Mapping Rules
[cite_start]To ensure statistical stability, fine-grained labels were collapsed into the following coarse analytical categories[cite: 113, 254]:

| Category | Mapping Source (PKU / UPOS) | Description |
| :--- | :--- | :--- |
| **n (Noun)** | n, nr, ns, nt, nx, nz / NOUN, PROPN | [cite_start]General, personal, and place names [cite: 255] |
| **v (Verb)** | v, vd, vn / VERB | [cite_start]Actional and verbal elements [cite: 256] |
| **a (Adjective)** | a, ad, an / ADJ | [cite_start]Qualitative and descriptive modifiers [cite: 257] |
| **d (Adverb)** | d / ADV | [cite_start]Adverbial modifiers [cite: 144] |
| **t (Temporal)** | t / (Preserved from PKU) | [cite_start]Time-related indicators [cite: 116] |
| **f (Locative)** | f / (Preserved from PKU) | [cite_start]Spatial orientation and locatives [cite: 116] |

[cite_start]*Note: Content words include n, v, and a[cite: 144, 186]. [cite_start]Function words follow Wang Li’s grammatical classification[cite: 143].*

## Repository Content
* **`Beiyou_shi_Annotations.xml`**: The primary dataset in XML format, utilizing an inline slash tagging structure (`word/tag`). It preserves poem-level metadata and line-level structures derived from the TEI source.
* [cite_start]**`Beiyou_shi_PoS_Dataset.csv`**: A token-level dataset providing the complete sequence of original model outputs and the final adjudicated tags for each poem[cite: 111, 167].
* [cite_start]**`Beiyou_shi_Visualization.html`**: An interactive visualization showing the tagging results for all 322 poems[cite: 164].

## Analytical Framework
[cite_start]The dataset is organized to support stratified analysis across four major poetic forms: Ancient-style verse, Seven-character regulated verse, Five-character regulated verse, and Seven-character quatrains[cite: 65, 66]. [cite_start]Quantitative indicators include poem-level proportions ($P_{i,k}$), content-to-function ratios, and positional distribution density across fixed-length lines[cite: 128, 157, 204].

## License
The dataset and documentation in this repository are licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/).

## Contact
**Xiang Wei**
PhD Candidate at Temple University, e-mail:x130319@gmail.com

***
