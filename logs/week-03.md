# Week 3

**Dates:** 07-06 to 07-10

## Goals
A more critical look at implementation has shown the the previous approach was likely too resource intensive. While many of models were described as real time, processing 15-20 frames per second, this was on server-grade GPUs. The cost of these would be prohibitive for creating accessible technology and approaches.

The goal for this week is to focus on user privacy and examine the viability of developing a process that remains on device for the duration of interaction with the user.

Learning goals:
1. Mobile exclusive SLAM implementations.


## Approach and Implementation

The broad, shallow knowledge gained the previous two weeks will be used to inform a deeper search targeting approaches that have been taken to SLAM exclusively on mobile devices. The previous proposed architecture was edge assisted, or split between a mobile phone and a server. The next will be mobile exclusive.

## Results

While it turns out that there have been many mobile exclusive approaches, these seem to be relegated to visual odometry (camera based step calculation) and AR/VR. The most meaningful AI approach has been implementation of a pipeline family named ORB-SLAM. This uses a particular kind of point tracking description for image matching named ORB. This is a classical CV approach that utilizes no machine learning or neural networks. Because of this, it is quite cheap resource wise.

It seems that while today's phones are powerful computation wise, they lack the capacity need for many neural nets (NNs) and come with the added challenges of heat dissipation and memory space. Seeing that approach as a dead end, an semantics or text based approach was inspired by a [paper](https://arxiv.org/pdf/1802.03510) that implemented search through 227k images on a phone via extreme compression. In that paper each image was stored as a 4096 bit vector. This allowed similarity comparison with high speed and low memory usage. All 227k descriptors were stored in under a gigabyte.

While the above paper was not semantic is highlighted the storage differences between data types. Images are quite intensive but words, numbers, and text are less so. This reduction in storage size would also result in significantly less expensive comparison operations for finding matches.

If this approach had sufficient accuracy, it would allow us to bypass the processing limitations of phones.




