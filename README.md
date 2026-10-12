# CAP 4620 Lab 1: Supervised Learning (Rat, Dog, or Lion?)

**Submitted by:** Carlita Coleman

## Summary

This project demonstrates supervised machine learning by training a decision tree classifier to identify an animal as a Rat, Dog, or Lion based on its physical features.

## Dataset

The dataset contains 150 synthetic animal examples, with 50 examples for each class.

The model uses three features:

* `weight_kg`: animal weight in kilograms
* `height_cm`: animal height in centimeters
* `tail_to_body`: tail-to-body ratio

The dataset is divided into training and testing sets using a 70/30 split:

* Training examples: 105
* Testing examples: 45

## Model

A `DecisionTreeClassifier` from scikit-learn is used with a maximum depth of 3 and a random state of 42.

## Results

* **Test accuracy:** 100% (1.000)
* **Model classes:** Dog, Lion, Rat
* **Saved model:** `models/decision_tree.joblib`
* **Model information:** `models/model_info.json`

The trained model correctly classified all 45 examples in the test set during this run. The saved model was also loaded successfully and predicted **Lion** for the example input.

## Discussion

Supervised learning uses labeled examples to learn patterns that can be used to predict labels for new data. A decision tree makes predictions by applying rules based on feature values.

The model's 100% test accuracy is a result on this synthetic dataset and does not guarantee the same performance on real-world animal data. Because the model was trained only on Rats, Dogs, and Lions, it is not designed to reliably identify other animal types.

Discussion Questions

1. Why are labels important in supervised learning?

Labels provide the correct answers during training. The model uses the labeled examples to learn patterns between the input features and the animal categories.

2. What would happen if the model were trained without labels?

Without labels, this would be an unsupervised learning task rather than supervised classification. An algorithm might group similar animals together, but it would not learn directly from known Rat, Dog, and Lion answers.

3. What might happen if the model were given a cat?

Cats are not among the three classes in the training data. The classifier would still likely assign the cat to Rat, Dog, or Lion, even though none is correct. This illustrates the limitations of using a classifier on an unfamiliar class.

4. Which feature does the decision tree use for its first split?

The first split is the feature shown at the root of the saved decision-tree diagram. It separates the training examples according to a learned threshold. Refer to figures/02_decision_tree.png to identify the exact feature and threshold.

5. What happens when max_depth is reduced from 3 to 1?

A depth-1 tree is simpler and makes fewer splits. It may fail to distinguish all three animal classes, so its accuracy may be lower than the depth-3 model. The actual accuracy should be verified by running the depth-1 model on the same test set.

## Project Files

* `SupervisedL.ipynb`: notebook containing the code and analysis
* `data/animals_full.csv`: complete dataset
* `data/train.csv`: training dataset
* `data/test.csv`: testing dataset
* `data/predictions.csv`: prediction results
* `models/decision_tree.joblib`: saved trained model
* `models/model_info.json`: model metadata
* `figures/`: project figures

## Tools and Libraries

* Python
* pandas
* scikit-learn
* Matplotlib
* joblib
* Jupyter Notebook # Lab 1: Supervised Learning