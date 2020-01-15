# Joint 3D Proposal Generation and Object Detection from View  Aggregation



## 0. Summary

xxxxxxxxxxxx

## 1. Research Objecive
xxxxxxxx

## 2. Background and Problems

xxxxxxxxxxxx

## 3. Method

point cloud and images--->feature maps--->3D object proposals--->extents, orientation and classification of objects
```mermaid
graph LR
A[point cloud and images] -- two extractors --> B[two feature maps]
B  -- RPN--> C[3D object proposals]
C  -- B-Box regression and classification--> D[extents, orientation and classification of objects]

```


## 4. Evaluation

a. with few proposals per frames, AVOD can achieve better recall than 3DOP and Mono3D
b. therefore: learning based approaches better than methods based on hand crafted features
c. MV3D  assigns wrong orientations for almost half of the cars, but AVOD assigns correct orientations for all cars
d. compare to Deep3DBox, AVOD enforces the superiority of fusion based methods over monocular based ones
e. compare to F-PointNet for feature extraction,  AVOD's extractor (encoder-decoder) better than the only encoder-extractor
f. weak: on the cyclist class, AVOD is worse than F-PointNet due to the low number of cyclist instances in the KITTI dataset, which induces a bias towards pedestrian detection in the joint pedestrian/cyclist network
g. less parameters than MV3D, approximately 16% of MV3D
h. processing frames faster than F-PointNet, e.g. pre-processing and inference
i. only 2 GB of GPU memory at inference time is enough

## 5. Conclusion
a. using a high resolution feature extractor coupled with a multimodal fusion RPN architecture
b. therefore, is able to produce accurate region proposals for small classes
c. the architecture employs explicit orientation vector regression to resolve the ambiguous orientation estimate inferred from a B-Box

## 6. Notes

xxxxxxxxxxxxxx

## 7. References

xxxxxxxxxxx
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NzIyMjczMzNdfQ==
-->