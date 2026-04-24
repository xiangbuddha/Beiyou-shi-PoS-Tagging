
***

# A Stratified Part-of-Speech Tagging Dataset of the *Beiyou shi*

## Introduction
This repository provides a comprehensive part-of-speech (PoS) tagging dataset for the *Beiyou shi* (北遊詩) by Chushi Fanqi (楚石梵琦). The analytical corpus comprises 322 poems, all of which are derived from a meticulously curated **TEI-encoded critical edition** of the text. This foundational TEI edition is available at: [https://github.com/xiangbuddha/-TEI--Beiyou-shi-TEI](https://github.com/xiangbuddha/-TEI--Beiyou-shi-TEI). 

The primary objective of this project is to provide a structured, reproducible linguistic profile of this collection, anchored in its digital philological source, and to facilitate further quantitative and comparative studies in Classical Chinese literature.

## Methodology and Tagging Workflow
The dataset was constructed using a three-layer tagging framework to ensure high accuracy and stability in processing Classical Chinese poetic language.

1.  **Initial Processing**: Word segmentation and tagging were initially performed using HanLP’s multi-task model for Classical Chinese, which generated two sets of raw labels: Universal PoS (UPOS) and PKU-style tags.
2.  **Lexicon-based Correction**: I applied a domain-specific lexicon (containing Buddhist terminology and proper nouns) and a correction table derived from a manual audit of the text to override recurring model errors.
3.  **Dynamic Adjudication**: I implemented an adjudication procedure where UPOS and PKU tags served as complementary inputs. Conflicts were resolved through fixed priority rules—such as preserving PKU-style temporal and locative distinctions—and local contextual evidence to determine the final analytical tag for each token.

## Mapping Rules
To ensure statistical stability, fine-grained labels were collapsed into the following coarse analytical categories:

| Category | Mapping Source (PKU / UPOS) | Description |
| :--- | :--- | :--- |
| **n (Noun)** | n, nr, ns, nt, nx, nz / NOUN, PROPN | General, personal, and place names |
| **v (Verb)** | v, vd, vn / VERB | Actional and verbal elements |
| **a (Adjective)** | a, ad, an / ADJ | Qualitative and descriptive modifiers |
| **d (Adverb)** | d / ADV | Adverbial modifiers |
| **t (Temporal)** | t / (Preserved from PKU) | Time-related indicators |
| **f (Locative)** | f / (Preserved from PKU) | Spatial orientation and locatives |

*Note: Content words include n, v, and a. Function words follow Wang Li’s grammatical classification.*

## Repository Content
* **`Beiyou_shi_Annotations.xml`**: The primary dataset in XML format, utilizing an inline slash tagging structure (`word/tag`). It preserves poem-level metadata and line-level structures derived from the TEI source.
* **`Beiyou_shi_PoS_Dataset.csv`**: A token-level dataset providing the complete sequence of original model outputs and the final adjudicated tags for each poem.
* **`Beiyou_shi_Visualization.html`**: An interactive visualization showing the tagging results for all 322 poems.

## Analytical Framework
The dataset is organized to support stratified analysis across four major poetic forms: Ancient-style verse, Seven-character regulated verse, Five-character regulated verse, and Seven-character quatrains. Quantitative indicators include:
* **Poem-level Proportions ($P_{i,k}$)**: Relative frequencies of PoS categories within each poem.
* **Content-to-Function Ratio**: A metric measuring the balance between image-bearing content words and structural function words.
* **Positional Distribution**: An examination of PoS density across character positions within fixed-length lines.

## License
The dataset and documentation in this repository are licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/).

## Contact
**Xiang Wei**
## Citation
If you use this dataset in your research, please cite it as follows:

Xiang. (2026). *A Stratified Part-of-Speech Tagging Dataset of the Beiyou shi* [Dataset]. GitHub. https://github.com/xiangbuddha/Beiyou-shi-PoS-Tagging
