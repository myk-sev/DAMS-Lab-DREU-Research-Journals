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


~~This will encompass:~~
~~1. Core: Paper rough draft.~~
~~2. Core: Complete app, test database results, model architecture, etc.~~
~~3. Core: Plan demo.~~
~~4. Stretch: Implement path finding mode for visual impairment accessibility.~~

## Approach and Implementation


In progress.


## Results

1. Core objects identified:door, door_handle, stairs, handrail, elevator_door, escalator, sign, fire_extinguisher, bulletin_board, security_camera, window, wall_clock, chair, table, whiteboard, cabinet, trash_bin, water_fountain, vending_machine, poster, light_switch, ceiling_light, fire_alarm, power_outlet, map.
2. Of 1.9m annotated Open Image v7 examples, 230k contain one of the labels above. Many labels (door, window, table) are common and not related to academics. To focus the set down to a scale affordable to run through a VLLM, label frequency was used utilized. Only images with a portion of 2 labels were kept and all with 3 labels or more. This gave a final set of 48k images.
3. 48k images were run through OpenAI's Luna at a cost of 2 cents per 100 images. This filtered the dataset down to 11k academic focused images containing at least two of the labels above.
4. DINO annotation complete.

## Notes

The balance between allowing room for growth in project understanding and test early/often is tricky. It was frustrating to find out that much of the research I had done on fitting improved DETR-EGTR performance onto a mobile phone had to be disregarded. Simultaneously, if I had been sure to constantly aim for a minimal viable product this could have been avoided.

Strong lesson.


