# AI & Security Project

## Sections

1. Project overview
1. Evaluating pretrained models prior to adding noise
1. Adding noise with FGSM

## Project overview

[project overview goes here]

## Evaluating pretrained models prior to adding noise

We started with evaluating several pre-trained models on our dataset to see how they perform reguraly. We used the weights that were optimised for ImageNet. As expected the pre-trained models performed pretty well.

Top-1 and Top-5 errors are the metrics we decided to use to evaluate the performance of the pre-trained classification models.

| Model     | Top-1 error | Top-5 error |
| --------- | ----------- | ----------- |
| ResNet18  | 24.00%      | 6.76%       |
| ResNet50  | 13.24%      | 1.96%       |
| ResNet152 | **8.34%**   | **0.64%**   |
| VGG16     | 21.92%      | 5.62%       |
| VGG19     | 21.18%      | 5.14%       |

For ResNet18, the model's top prediction is incorrect 24% of the time, and the correct class is not within the top 5 predictions 6.76% of the time.

For ResNet50, the model's top prediction is incorrect 13.24% of the time, and the correct class is not within the top 5 predictions 1.96% of the time.
