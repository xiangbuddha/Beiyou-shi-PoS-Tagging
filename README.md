
***

# Reading Chushi Fanqi Through Selection: A Stratified Part-of-Speech Analysis of the *Beiyou shi*

## Introduction
This repository contains the dataset and methodological documentation for the research project "Reading Chushi Fanqi Through Selection: A Stratified Part-of-Speech Analysis of the *Beiyou shi*." The study utilizes quantitative linguistics to examine the internal literary features of the *Beiyou shi* (北遊詩) by Chushi Fanqi (楚石梵琦), using Qian Qianyi’s (錢謙益) selection in the *Liechao shiji* (列朝詩集) as a historically grounded comparative framework. 

The analysis is based on a closed historical corpus of 322 poems. By comparing the part-of-speech (PoS) distributions of selected and unselected poems, I explore how measurable linguistic features align with historical editorial judgments.

## Methodology and Tagging Workflow
The research design adopts a three-layer tagging framework to ensure high accuracy and reproducibility in processing Classical Chinese poetic language.

1.  **Initial Processing**: I used HanLP’s multi-task model for Classical Chinese to generate word segmentation and two sets of raw tags: Universal PoS (UPOS) and PKU-style tags.
2.  **Lexicon-based Correction**: A domain-specific lexicon for the *Beiyou shi* (containing Buddhist terminology and proper nouns) and a correction table derived from a manual audit of 150 poems were applied to override recurring model errors.
3.  **Dynamic Adjudication**: I implemented a script-based adjudication procedure where UPOS and PKU tags served as complementary inputs. Conflicts were resolved through pre-specified priority rules (e.g., preserving PKU fine-grained temporal/locative distinctions over broad UPOS categories) and local contextual cues.

## Mapping Rules
To reduce sparsity in the statistical analysis, fine-grained tags were collapsed into coarse analytical categories:

| Category | Mapping Source (PKU / UPOS) | Description |
| :--- | :--- | :--- |
| **n (Noun)** | n, nr, ns, nt, nx, nz / NOUN, PROPN | General, personal, and place names |
| **v (Verb)** | v, vd, vn / VERB | Actional and verbal elements |
| **a (Adjective)** | a, ad, an / ADJ | Qualitative and descriptive modifiers |
| **d (Adverb)** | d / ADV | Adverbial modifiers |
| **t (Temporal)** | t / (Preserved from PKU) | Time-related indicators |
| **f (Locative)** | f / (Preserved from PKU) | Spatial orientation and locatives |

*Note: Content words are defined as n, v, and a. Function words (adverbs, prepositions, conjunctions, particles, and interjections) follow Wang Li’s grammatical classification.*

## Repository Content
* **`Beiyou_shi_PoS_Dataset.csv`**: The complete token-level dataset. Columns include Poem ID, Original Line, Token, PKU-Tag, UPOS-Tag, and the Final Adjudicated Tag used in the study.
* **`Beiyou_shi_Visualization.html`**: An interactive visualization showing the line-level tagging results for all 322 poems.
* **`README.md`**: This documentation of research logic and tagging rules.

## Statistical Framework
The analysis employs poem-level proportions ($P_{i,k}$) to mitigate the influence of varying poem lengths. Differences between selection groups are assessed within four stratified poetic forms: 
* Ancient-style verse (古體詩)
* Seven-character regulated verse (七言律詩)
* Five-character regulated verse (五言律詩)
* Seven-character quatrains (七言絕句)

Robustness of observed differences is verified using Cohen’s $d$ effect sizes, non-parametric bootstrap confidence intervals (5,000 resamples), and leave-one-out sensitivity checks.

## License
The dataset and documentation in this repository are licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](http://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, provided that appropriate credit is given to the original research.

## Contact
**Xiang Wei**, PhD Candidate at Temple University.e-mail:x130319@gmail.com 
