# Week 7

**Dates:** 08-03 to 08-07

## Goals

Action Goals:
1. Core goal: Incorperate methods for imperfect text OCR matching (Levenshtein similarity).
2. Core goal: Test implementation on final location.
3. Stretch goal: Begin testing model on existing spare information environment data sets.
4. Unreasonable stretch: Complete a baseline version of the localization app.

Learning Goals:
1. Explore what scene updating/relearning could look like in a semantic environment.
2. Explore uncertainty aware SLAM ([Paper: PUF](https://arxiv.org/html/2607.07170v1))
3. Explore non-semantic based privacy approaches. ([Paper:CVPRW 2026](openaccess.thecvf.com/content/CVPR2026W/IMW/papers/Panek_Privacy-Preserving_Structureless_Visual_Localization_via_Image_Obfuscation_CVPRW_2026_paper.pdf))


## Approach and Implementation



## Results






## Notes
Research Exploration:
1. EGTR: Extracting Graph from Transformer for Scene Graph Generation [(link)](https://arxiv.org/pdf/2404.02072)
This paper is the base technology for the semantic approach. It intercepts the relationship weights within the self attention layer a vision encoder to look at objects before bounding boxes are created. It allows for skipping of triplet detection mechanism core to most semantic graph generators making the core mechanism faster and more efficient. This portion will be the most resource intensive section of our pipeline.
2. TextSLAM: Visual SLAM with Semantic Planar (Jul 2023) ([link](https://arxiv.org/pdf/2305.10029))
The core paper that started the current wave of use of text ocr in SLAM pipelines. Combines descriptors with text ocr for improved matching. Excellent visualizations for outcomes.
<img width="591" height="498" alt="image" src="https://github.com/user-attachments/assets/69e09999-507b-46d9-acdf-f65b120210ad" />
3.Robust Loop Closure by Textual Cues in Challenging Environments ([link](https://arxiv.org/pdf/2410.15869)) (Oct 2024)
A bit of a red herring. This paper utilized text ocr in combination with LiDAR to localize text and use that combination to close loops in mapping. Our pipeline will not have that feature.  The portions on use on consistency graphs to overcome the generic nature of some text ocr objects however was useful.
<img width="418" height="272" alt="image" src="https://github.com/user-attachments/assets/33a7daf3-e4ee-4210-8505-4d5a38b9a099" />


