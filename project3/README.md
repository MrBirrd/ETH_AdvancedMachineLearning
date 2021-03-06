# Project 3

## About
This project was a segmentation task. The right mitral valve should be segmented in ultrasonic videos.

## Dataset and Processing

The dataset cannot be published here, since it contains real samples from MitraSwiss. There were 60 videos in total, of which each video
only had 3 annotated frames, mostly by amateurs and low resolution. Only 10% of the dataset consisted of high-res videos. Those were annotated by experts.

The videos were first normalized to values from 0-1 and then downscaled to the lowest resolution in the dataset, which also occured the most. Then additional layers were generated, by adding one layer where the frame is median blurred and another layer that contains the masks generated by multiotsu or yen thresholding. This improved the results a lot. Then augmentation is used by shifting, rotating, zoom and changing the brightness.

## Model
UNET was implemented from scratch for this task and experimentations were made by adding more layers, squeeze-excite blocks or attention. The generated mask from thresholding the sigmoid output was further postprocessed by eroding and dilating.

## Results
The final submission ranked amongst top places again while having a quite simple approach (compared to more other UNET models like UNET++). I learned a lot about UNET in this project and its components like the importance of skip-connections.