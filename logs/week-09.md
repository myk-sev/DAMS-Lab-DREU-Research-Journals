# Week 9

**Dates:** 08-17 to 08-21

## Goals

Main goal: Address lack of overlap between DETR to EGTR object relation detection model and features present in academic settings.

EGTR the object object relationship predictor that sits on top of the DETR object identification model is trained with a small vocabulary. This small focus is what gives it sufficient efficiency to run on mobile devices. Unfortunately, this vocabulary is too small even when paired with text recognition. This breaks the basis of the project.

While this issue is not spoken to in the literature, it is clear that this is why the pipeline has not been used on low visual texture environments. All attempts to extend the power of the model through sequence integration, OCR integration, and key-frame selection have no use when the core model cannot detect the necessary objects to create a map of the space.

The logical and necessary addition to the literature in this scenario is the creation of a fine-tuned DETR-EGTR pair for academic corridor specific objects. To account for time left in the program, the new model will be distilled from grounded DINO annotations instead the creation of a custom data set.

Sub goals:
1. Identifying 25 objects common to academic corridors (drinking fountains, wifi routers, doors, signs, etc).
2. Parse through the Open Images v7 data set to identify ~100,000 images that contain the desired objects.
3. Send the above images through a VLLM to further extract out images specific to academic settings.
4. Annotation the final set of ~10,000 images using grounded DINO.
5. Utilize a object triplet GNN (subject-relation-predicate) to identify object relation ships in the images.
6. Fine-tune DETR on the grounded DINO annotations.
7. Fine tune EGTR compatibility with the new DETR model utilizing the new object triplets as the training labels.

In the event this is not successful, an existing classroom specific training data set has been identified. Steps 4-7 will be repeated on that dataset instead.


~This will encompass:
1. Core: Paper rough draft.
2. Core: Complete app, test database results, model architecture, etc.
3. Core: Plan demo.
4. Stretch: Implement path finding mode for visual impairment accessibility.~

## Approach and Implementation



## Results



## Notes


