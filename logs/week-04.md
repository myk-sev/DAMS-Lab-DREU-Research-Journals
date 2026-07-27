# Week 4

**Dates:** 07-13 to 07-20

## Goals
Use of semantic approaches seems as though it could bridge the gap of making a neural net based SLAM pipeline possible on to run exclusively on mobile.

Action Goals:
1. Review the literature on semantic (text) based SLAM and approaches that incorperate text ocr to supplement the result.
2. Identify research gaps in the area.
3. Ensure the methods can be run on mobile.
4. Plan a mobile compatible pipeline based on semantic and text approaches.

Learning Goals:
1. Scene building methods that are semantic first rather than supplementing. ([Paper: LangLoc](https://arxiv.org/pdf/2607.05077))
2. Past incorperation of text ocr into semantic models ([Paper: Text In Place]((https://arxiv.org/html/2503.06501v1)) ([Paper:SceneGATE]((https://arxiv.org/pdf/2212.08283))

## Approach and Implementation

Inspired by a meeting with Dr. Yus emphasizing the privacy value of an on phone implementation this week focused on a semi structured exploration of on phone approaches focused on semantic based mapping. This particular approach has very low information requirements making it particulary mobile suited.

A list of papers to examine was created, refined through exploration, and used to construct a set of notes and list of future papers to examine.

## Results

It appears that this is a well developed field with several iteration in approaches. Some of the earliest stages were CNN based with visual models used to generate and apply semantic meaning. As AI models advanced those techniques advanced as well with transformer based models and then visual large language models or VLLMs being applied. Each of these approaches allowed for increased granualarity of the vocabulary used to describe objects and the relationships between them. VLLMs in particulary were able generate entire paragraphs that could be used to reconstruct scenes.

With each generation of approaches the resource requirement increased as well. For the scope of this project it looks like the tranformer approaches may be usable for real time processing on mobile with classic CNNs such as DINO and ResNet as fallback.

Text OCR was interesting as well. Research here surfaced complexities in handling text matching across challenging orientations and conditions. As with above, more resource intensive models are better equipped to handle motion blur and imperfect lighting along with decoding the artistic code within signs.

Ultimately, it looks like it is more than possible to run models of sufficient complexity completely on mobile with fall backs in the event of failure.

The goal architecture will now focus on a pipeline consting of RT-DETRv2-M -> EGTR for generation of the semantic relation graph. A text OCR model for sign contents extraction (this is still be decided on during week 5 ). Bound boxes will be used to determine where the text information will be inserted. Normalized Levenstein similarity will be used to match extracted text across imperfect readings (1eft vs left) and an embedding to cross attention layer format will be used to match scene graphs to larger room & map graphs.

For the mobile portion onboard MUI will be used to decrease the search area by tracking motion and ML model will be run on an dedicated library called CoreML on iOS. This allows for greater resources access than what could be utilzied through a browser implementation.

## Notes

[Week 4 - Combining TextOCR and Semantic Relation Maps](https://github.com/myk-sev/DAMS-Lab-DREU-Research-Journals/blob/main/Week%204%20-%20Combining%20TextOCR%20and%20Semantic%20Relation%20Maps.pdf)
[Week 4 - Language (Semantics) for Privacy Preservation](https://github.com/myk-sev/DAMS-Lab-DREU-Research-Journals/blob/main/Week%204%20-%20Language%20(Semantics)%20for%20Privacy%20Preservation.pdf)
[Week 4 - Text OCR](https://github.com/myk-sev/DAMS-Lab-DREU-Research-Journals/blob/main/Week%204%20-%20Text%20OCR.pdf)


