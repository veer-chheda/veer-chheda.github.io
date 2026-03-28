---
title: "Color Space Fusion for Semantic Segmentation in Indian Adverse Weather Driving Scenes"
date: 2026-01-17
author: ["Veer Chheda", "Vansh Shah", "Hezal Lopes", "Vishakha Shelke"]
description: "Performing semantic segmentation in bad weather
conditions is still extremely difficult because RGB sensors often
have poor visibility in such conditions. In this study, we have
explored various colour spaces to combine RGB and Near-
Infrared images to improve the perception of environment in
bad weather conditions. We assessed the YUV, LAB and HSV
colour spaces to combine RGB and NIR images along with an
RGB baseline for comparison. The IDD-AW dataset was used for
this fusion across the YOLOv8 and YOLOv11 nano and small
segmentation models. According to our experimental results,
LAB fusion along with YOLOv11 yields the best results which
had a SmIoU of 17.96 and a mIoU of 26.46. These results are
a 10% improvement over the RGB baseline. Since YUV and
LAB color spaces have separate luminance channels, they have
higher scores when compared to HSV, which shows moderate
improvements. This tells us that choosing the right color for
space for the RGB and NIR fusion has a huge positive impact
on semantic segmentation in conditions with fog, low light, rain
and snow even for smaller models focusing on real-time inference."
editPost:
  URL: "/papers/iddaw_segmentation.pdf"
  Text: "6th Biennial International Conference on Nascent Technologies in Engineering, IEEE Xplore"
tags: ["Computer Vision", "Semantic Segmentation", "RGB-NIR Fusion"]
---

## Abstract

Performing semantic segmentation in bad weather
conditions is still extremely difficult because RGB sensors often
have poor visibility in such conditions. In this study, we have
explored various colour spaces to combine RGB and Near-
Infrared images to improve the perception of environment in
bad weather conditions. We assessed the YUV, LAB and HSV
colour spaces to combine RGB and NIR images along with an
RGB baseline for comparison. The IDD-AW dataset was used for
this fusion across the YOLOv8 and YOLOv11 nano and small
segmentation models. According to our experimental results,
LAB fusion along with YOLOv11 yields the best results which
had a SmIoU of 17.96 and a mIoU of 26.46. These results are
a 10% improvement over the RGB baseline. Since YUV and
LAB color spaces have separate luminance channels, they have
higher scores when compared to HSV, which shows moderate
improvements. This tells us that choosing the right color for
space for the RGB and NIR fusion has a huge positive impact
on semantic segmentation in conditions with fog, low light, rain
and snow even for smaller models focusing on real-time inference.

