# BioScout's 2024 Data Engineer Technical Challenge

Welcome to our technical challenge for the data engineering role at BioScout, you have been given a small subset of the
type of data we work with and some analogous problems to solve that we deal with in our data pipelines.

## Your Tasks

### Installation

You have been given an installable python package called `bioscout-tech-challenge` which is built using `poetry`.

Run the following to install the package (assuming you have poetry available as a package on your python interpreter):

```shell
poetry install
```

You can then run the following to see the cli (built using the `cli` module) in action:

```shell
bioscout-tech-challenge hello
```
---------------------------------------------------------------------------------------------------------------------

### Introduction & Submission Instructions

We're asking you for a mixture of data processing, data analysis, and machine learning model evaluation tasks. We're 
looking for your ability to add features to an existing python library as well as your data exploration skills. Feel 
free to add features to the package so that they're accessible via the cli or are helpful modules and methods for use
in your jupyter notebook (or equivalent tool of choice) exploration of the data we've provided.

Be creative with the tools and solution to the problems, this is the time to show off your skills and show the diversity
and excellence of your engineering talents. Do what you think is best and be willing to back your ideas in the follow-up
discussion of your solution, we're excited to discuss your design choices and why you have solved the problems the way
you have.

Please write your solutions as additions / features to the `bioscout-tech-challenge` package, to the standard that 
you'd be happy to put up a PR for review. Any additional writing or analysis is welcomed, please note where to find this
work for each task so that it can be reviewed in your submission

*Note there is a `cli` module already written for you and a bounding box class already created for you within the 
`models` module. We're expecting you to expand upon the `bioscout-tech-challenge` software package and implement a 
design that helps you solve the problems we've put in front of you. We're expecting a working solution to all these 
problems, please make sure your solution runs and is easily re-executable, i.e. dependencies are managed, the cli is
easy to use etc.*

#### How to Submit

Please create a GitHub repository and invite [BioScoutNick](https://github.com/BioScoutNick) so that we can see your
work. We're keen to see a healthy changelog and sensible checkpoints of progress, in order to keep your repo small,
don't worry about committing the original data files we've given you unless you've done some feature engineering or
modifications that necessitate adding them to the repo.


### 1. Pre-Process Weather Data

We've got some weather data in from our new weather system, but it's not easy to query the data, flatten the structure
so that each observation has its own row and every attribute is in its own column. Join the weather observations onto
the device data so that each weather reading has the associated device metadata attached to it. Provide descriptions of
the new data columns and deduce the purpose and origin of this new data.

Save this data somewhere sensible and note in this readme where it can be found so it can be reviewed in your submission

### 2. Visualise Weather Data & Provide Insights

Now that you've pre-processed this weather data into something usable, visualise the various sensors and their data over
time, explain any insights or interesting observations you have about the data. What would you conclude from how the 
sensors are behaving out in the field? 

Write up your analysis and note in this readme where to find what you've written so that it can be evaluated for 
submission.


### 3. Explore Imagery & Bounding Boxes

There are a bunch of images, and a bunch of bounding boxes for a new disease we want to deliver for customers. 
There are some human, and some machine made bounding boxes are provided, there are a couple of tasks to complete here:
 - Suggest & compute performance metrics for the model, 
 - Suggest a confidence threshold cutoff we should use to maximise these metrics.
 - Show areas where the model has made mistakes + explain what has happened.
 - Advise on how you might solve the mistakes the model is making and what we should do to improve the model in the 
    future
 - How could we improve our annotations etc.?

The human annotations are stored as absolute x_min,x_max, y_min, y_max values, and the machine made predictions are 
stored as normalised middle x, middle y values, and normalised width and height values relative to the size of the 
image; the model also has confidence scores attached, these are represented as a float between 0 and 1 for low and high
confidence respectively.

Normalised middle x and middle y values mean that the x & y floats represent the middle of the box relative to the size
of the image, so a middle x value of 0.5 means the center of the bounding box is in the dead center of the image, and a
normalised width of 0.5 means the width of the bounding box is half the width of the image, you can apply the same
logic for the y and height values etc.

## What We're Looking For

Here is how we will evaluate your response, we are looking for the following

- Efficient Problem-Solving
  - We need to solve novel problems and an ability to scope and shape what the crux of an issue is, as well as apply the
    correct solution. This is at the heart of being a great engineer. We want to see that, with re-usability in mind, we like
    to solve problems once and rely on the foundations of yesterday. Being comfortable adding capabilities to the 
    library we've provided and using them within your exploratory jupyter notebook for exploration is a good example of
    applying the right tool for the right job and code re-use.

- Solid Software Engineering Principles
  - We ship and maintain what we write. We're looking for characteristics of code you'd be happy to revisit in the 
    future and rely on while you sleep. We are scaling up, and we are looking for engineers who write robust software.
  - In particular, we're looking for foundational skill-sets such as:
    - Automated Testing
    - Version Control Comfortability
    - Good Software Design
    - Clear Documentation & Easy to Follow Logic
    - Knowledge of Python & Available Packages
  - Don't go overboard on trying to prove out every one of these principles, we can discuss your knowledge of these
    within the final interview, but it certainly doesn't hurt to show off what you know. Having some automated tests
    proving your submission is correct will always score brownie points for example so don't stop yourself from showing
    great work.

- Creativity
  - Show off interesting ideas or questions you can think of with the data we've given you, whether that be interesting 
    correlations or different ways to visualise what we've provided. Even the kinds of models or forecasting you'd like
    to do if you had more data. We have fascinating data at BioScout that requires a creative mind to explore and mine.
    We do world first research on the data we capture. BioScout is an exciting place when you're energised by the 
    'what if' and you're thinking of what is possible in the future with the incredible data we have. We'll be looking
    for pontification of fascinating insights you can either extract from what we've given you or you have thought of
    could be possible with some data augmentation from other sources.
  - If you have your favourite libraries or tools you think solve these problems or could enhance what we've presented
    here we're keen to see them, show off your favourite tools.

- Data Engineering/Science Skills
  - Data Communication
    - Our data is fundamentally novel and exciting. A big responsibility in the data team is to effectively communicate 
      your findings and insights to a broader audience, both internal and external to the company. You are often talking
      to very smart but not necessarily data native stakeholders. An ability to distil but not dumb down your knowledge 
      so that its easy to meaningfully understand by a diverse audience is key.
  - Data Engineering
    - Your ability to manipulate, transform, explain, and maintain data is ultimately what decides how good our models
      are and is what limits our ability to analyse and research our datasets. The more efficiently you can engineer our
      data for what we need it for, the better we can solve the problems we want to address.
  - Data Science
    - We have lots of data, and we want to research and mine it for new answers to interesting questions only we can 
      answer. Whilst this is a data engineering role, its important you feel comfortable interrogating your data for 
      issues of quality or inconsistency. These skills happen to be the same as the kind of analysis we'll need to do 
      from a data science perspective.

**If at anytime you have any questions or feel there is any ambiguity in these instructions, and you'd like 
clarification, please feel free to email nick at nicholas@bioscout.com.au who you interviewed with. He'll be happy to
answer any queries you have, there's also no penalty for asking questions, we want you to have all the information you
need, we're looking for quality and clarity.**






## DANIELE'S NOTES 

***EXPLAINING HOW MY PIPELINE WORKS***
You can run the code Main.ipynb on jupyter-notebook or run it from shell. From Main.ipynb we trigger the codes global_variables.ipynb, ./functions.ipynb and data_analysis_and_visualization.ipynb. 

In the global_variables.ipynb there are only variables to located human and model boxes files and output folder. 

The functions.ipynb only contains the functions I used. 

The data_analysis_and_visualization.ipynb process the data and shows a few plots. 

The Main.ipynb runs a pipeline which will provide a folder called output_images or output_images_run_#. The folder will contain the images with the human and model boxes with confidence level. Boxes of false positives are also shown. 

The pipeline also provide metrics and suggests a threshold cutoff for maximing the metrics. In the main folder there is also a missed detections and false positives file (missed_detection_&_false_positives.csv)


In the main folder you will also find two other codes: 

- The Exploration.ipynb code which does more or less the same operations done by the Main.ipynb code. It is just an exploration code not fundamental for running the pipeline. 

- The Main.nbconvert.ipynb is just produced in case you want to run the pipeline from shell. This is code is not different from the Main.ipynb code. 



### 2. Visualise Weather Data & Provide Insights

The processed data are available in the csv file called ***"preprocessed_weather_data.csv"***

I analyzed the behavior of pressure and Value against time, longitude, and latitude for each device. The data covers October and November 2024, although some sensors only recorded data in November. The sensors WH-0012, WH-0015, WH-0003, WH-0011, WH-0014, WH-0006, WH-0016, WH-0017, and WHH-0010 have data for both October and November. The device WH-000001 only recorded data in October, while the remaining devices recorded data exclusively in November.

The overall trend indicates a rise in pressure, peaking on 2024-10-10. After this peak, there was a decline, followed by a higher peak on 2024-10-19. In November, the pressure behavior became more erratic, with frequent fluctuations. Some sensors, like WH-0020 and WH-0017, displayed a downward trend. Interestingly, most sensors recorded their highest pressure on 2024-11-20.

The sensor with the highest pressure in October was WH-0012, with a value of 10.3K, while the lowest pressure was recorded by WH-0010 in November.

The Value attribute displayed a stochastic pattern across all devices, with the mean value remaining relatively constant over time. A plot of Value vs. Time (Julian date) indicates a general trend around a value of 10, which is corroborated by a quick calculation of the mean Value across all data in Python, yielding a value of 11.03.

An analysis of pressure and Value against longitude and latitude showed no distinct trends.




### 3. Explore Imagery & Bounding Boxes

### Show areas where the model has made mistakes + explain what has happened.


We can identify two types of errors in the model:

**1. FALSE NEGATIVES (missed  detections)**

**Description**: 

This occurs when the model fails to detect an object that is present in the image, either by not producing a bounding box or by generating a box that doesn't sufficiently match the human-annotated one (low Intersection over Union, IoU).
Visual Indicator: Areas where human annotations (in red) are present but the model either doesn't produce a bounding box or its predicted box doesn't match the ground truth.

Potential Causes are the following listed below: 

a. **High confidence threshold** as if the threshold is too high, the model may discard valid detections.

b. **Poor generalization** (struggles with rare, small, occluded, or low-contrast objects).

c. **Inadequate training data** as probably the model did not encounter enough examples of certain objects or scenarios.

d. **Low image quality** as poor resolution or blurry images can hinder accurate detection.



**2. FALSE POSITIVES (incorrect detections)**


**Description:** 

False positives occur when the model detects objects that aren't actually present, generating bounding boxes that don’t correspond to real objects (i.e., no match with human annotations or insufficient IoU).

**Visual Indicator:** 
Areas where the model's predictions (in blue) do not align with any human-annotated box or have very low IoU with ground truth boxes.

**Potential Causes:**
Overfitting to background noise: The model may mistake background patterns or irrelevant features as objects.

**Low confidence threshold:**
A low threshold may cause the model to classify ambiguous or background areas as objects.

**Incorrect bounding box generation:** 
The model might generate poorly sized or mispositioned boxes, leading to poor overlap with ground truth.



### Advise on how you might solve the mistakes the model is making and what we should do to improve the model in the 
###   future

**Suggested Solutions for FALSE NEGATIVES:**

**Lower the confidence threshold:** Reduce the threshold to allow more boxes to be considered valid, addressing missed detections due to overly confident predictions.

**Improve generalization:**

**Data Augmentation:** Use techniques like cropping, rotation, and color adjustments to expose the model to more diverse scenarios.

**Increase data diversity:** Add more examples of underrepresented objects to balance training data and improve detection.
Use a more powerful model: Consider advanced models like YOLO, Faster R-CNN, or DETR, or fine-tune a pre-trained model on a larger dataset.

**Increase image resolution:** Ensure high-quality input images to match the model’s training conditions and avoid performance drops.




**Suggested Solutions for FALSE POSITIVES:**

**Increase confidence threshold:**
Filter out low-confidence detections to reduce false positives.

**Improve localization:**

**Anchor box adjustments:** Optimize sizes and ratios for better predictions.
Post-processing tweaks: Adjust Non-Maximum Suppression (NMS) to remove duplicates.
**Regularization:** Use techniques like dropout to prevent overfitting.
**Reduce background noise:** Focus on object areas using segmentation models.

**Model Improvement for Future Use:**

**Data Improvements:**

**Increase diversity:** Add varied object types, lighting, and backgrounds.
More annotations: Manually annotate more images to improve performance.
Model Enhancement:

**Advanced architectures:** Use YOLOv5, EfficientDet, or DETR for better accuracy.
**Ensemble methods:** Combine multiple models to reduce errors.
**Fine-tuning:** Tailor models to specific tasks with transfer learning.

**Interpretability:**

**Explainability tools:** Use Grad-CAM or SHAP to identify error patterns.


In general, to improve the model an efficient compromise for reducing false nagetives and false positives is necessary. I am referring especially to managing the confidence threshold. Increasing the confidence threshold may reduce false positives but increase false negatives. Decreasing the confidence threshold may reduce false negatives but increase false positives. 




### How could we improve our annotations etc.? ###



***Regular Updates of Annotations:***
Keep track of any changes in object appearance, positioning, or other factors over time. This is particularly important for dynamic environments (e.g., different seasons, lighting, or scenarios).

***Multiple Annotations per Image:***
Use multiple human annotators to annotate the same image and then compare results. If annotators agree, the annotation is considered valid; if there are discrepancies, a review process can be triggered.

***Data Augmentation:** Use techniques like cropping, rotation, and color adjustments to expose the model to more diverse scenarios.

***Increase data diversity:*** Add more examples of underrepresented objects to balance training data and improve detection.
Use a more powerful model: Consider advanced models like YOLO, Faster R-CNN, or DETR, or fine-tune a pre-trained model on a larger dataset.

***Increase image resolution:*** Ensure high-quality input images to match the model’s training conditions and avoid performance drops.

**Synthetic Data Generation:** Use augmentation techniques like rotation, flipping, scaling, and translations to create new training examples. This helps improve the model's robustness.






    
