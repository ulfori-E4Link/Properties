# objectcount

Detection and counting of objects inside video frames, built on Keras and the TensorFlow graph runtime.

## Live footage

---

### Running totals across a stream

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" | width=418> <img src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" | width=400>
</p>

---

### Counting frame by frame

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" | width=410> <img src="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" | width=410>
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" | width=410><img src="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" | width=410>
</p>

---

### Following a subject across frames

---

### Counting inside a still picture

---

### Detector built on R-CNN

### Segmentation plus counting with Mask R-CNN

---

### Rolling your own counter

Training on your own footage is the fastest route to a tailored model. Two worked examples cover the transfer-learning basics and show a full end-to-end run.

**Example A: counting plush toys**

Sources live in the training folder of this repository.

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" | width=750>
</p>

**Example B: counting pasta boxes**

Training material ships alongside the segmentation sample.

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/62903429-46e3df00-bd6b-11e9-9f97-4de477fa8769.png" | width=750>  
</p>

---

***Work in progress — a leaner build and expanded docs land in this repo soon.***

- ***Notebook walkthroughs for the common paths are queued.***

A case study that drives the same counters over road footage is linked from this repo.

---

## How to drive it

### 1.) Running totals

#### 1.1) Pedestrians, colour prediction switched off

*Setup used for the pedestrian clip:*

    is_color_recognition_enabled = False # flip to true to enable colour prediction
    roi = 385 # position of the counting line
    deviation = 1 # width of the counting band

    counter_api.cumulative_object_counting_x_axis(input_video, detection_graph, category_index, is_color_recognition_enabled, roi, deviation) # tally every object

*What that clip produces:*

 <p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" | width=700>
</p>