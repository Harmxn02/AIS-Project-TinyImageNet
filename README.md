# AI & Security Project

## Sections

1. Project overview
1. Evaluating pretrained models prior to adding noise
1. Adding noise with FGSM

## Project overview

[project overview goes here]

## Evaluating pretrained models prior to adding noise

We started with evaluating several pre-trained models on our dataset to see how they perform reguraly. We used the weights that were optimised for ImageNet. As expected the pre-trained models performed pretty well.

### Evaluation metrics

Top-1 and Top-5 errors are metrics used to evaluate the performance of classification models, particularly in the context of image recognition tasks.

#### Top-1 Error

Definition: The Top-1 error rate is the proportion of test samples for which the model's top prediction (the class with the highest predicted probability) is incorrect.
Example: If the model predicts the class "cat" for an image of a dog, this counts as a Top-1 error.

#### Top-5 Error

Definition: The Top-5 error rate is the proportion of test samples for which the correct class is not within the top 5 predicted probabilities.

Example: If the correct class "dog" is not among the top 5 classes predicted by the model, this counts as a Top-5 error.

### Why Use These Metrics?

Top-1 Error: This metric is straightforward and indicates how often the model's most confident prediction is wrong.

Top-5 Error: This metric is useful for understanding how well the model can narrow down its predictions to a small set of likely classes, which is particularly helpful in datasets with a large number of classes.

### Example in Context

Using our actual evaluation results we can compare the different models. In our case **ResNet152** performed the best

| Model     | Top-1 error | Top-5 error |
| --------- | ----------- | ----------- |
| ResNet18  | 24.00%      | 6.76%       |
| ResNet50  | 13.24%      | 1.96%       |
| ResNet152 | **8.34%**   | **0.64%**   |
| VGG16     | 21.92%      | 5.62%       |
| VGG19     | 21.18%      | 5.14%       |

For ResNet18, the model's top prediction is incorrect 24% of the time, and the correct class is not within the top 5 predictions 6.76% of the time.

For ResNet50, the model's top prediction is incorrect 13.24% of the time, and the correct class is not within the top 5 predictions 1.96% of the time.

These metrics help in comparing the performance of different models and understanding their accuracy in classification tasks.
