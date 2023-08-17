# Rating Predictor App using Gradio and Transformers from HuggingFace (BERT)

![App Demo](https://github.com/hsr-22/RatingPredictor_HF/blob/main/app_demo.png)

This repository contains code and resources for a Rating Predictor App that utilizes the Hugging Face's Gradio library and Transformers library with BERT for sentiment analysis. The app takes input in the form of reviews and predicts the corresponding rating (1 to 5 stars) based on the sentiment of the review.

## Table of Contents
- [Dataset](#dataset)
- [Prerequisites](#prerequisites)
- [Process Overview](#process)
- [Challenges](#challenges)

## Dataset
I have used the [Yelp Reviews](https://huggingface.co/datasets/yelp_review_full) Dataset for this model.

The Model after fine-tuning has been saved [here](https://drive.google.com/drive/folders/1FX8Gjbbq_qFze5TCjDEmOFkH5rOHUB1X).

## Prerequisites
Before you begin, ensure you have the following prerequisites:
- Python (>=3.6)
- Pip package manager

## Process Overview
1. Install the required libraries (datasets, transformers, gradio, accelerate, evaluate)
2. Next, load the dataset ```yelp_reviews_full``` from ``datasets``
3. Load tokenizer from the pre-trained BERT Model
4. Next, fine-tune the model using Sequence Classification and then train the model using the labels created.
5. Finally, after training the model, save the model locally and then load it for your specific application.
6. In the specific task, create a tokenizer function to process the user inputs and return the output (In my application, I have given the confidences corresponding to each label as the output.)
7. Next, simply launch your model using Gradio GUI. 

   **And, we're done**

Now, enter any review text relating to a topic of your choice and click the "Submit" button. The app will process the input using BERT-based sentiment analysis and provide a predicted rating. 

## Challenges
Any project cannot be completed without facing challenges.
Some of them which might be helpful in future are
- Converting a tensor to a numpy array if using argmax for prediction
- Installing accelerate after importing transformers causes issues. It is better to install all libraries together at the start.
- If you are using GPU acceleration, then you need to add ``.to('cuda') `` in ``predictions`` to be able to predict successfully.

Enjoy! 🚀
