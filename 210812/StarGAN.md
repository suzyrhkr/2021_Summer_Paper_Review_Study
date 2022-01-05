# StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation

## Abstract
Image -to-Image Translation:
existing approaches have limited scalability and robustness in handling more than two domains, since different models should be built independently for every pair of image domains.    
To address this limitation, we propose StarGAN, a novel and
scalable approach that can perform image-to-image translations for multiple domains using only a single model.

## Introduction
The task of image-to-image translation : To change a
particular aspect of a given image to another, e.g., changing the facial expression of a person from smiling to frowning.   

However, existing models are both inefficient and ineffective in such multi-domain image translation tasks.

### Terms:
- attribute: a meaningful feature inherent in an image such as hair color, gender or age   
- attribute value: a particular value of an attribute, e.g.,
black/blond/brown for hair color or male/female for gender   
- domain: a set of images sharing the
same attribute value   


### Conributions:
-  Proposed StarGAN, a novel generative adversarial
network that learns the mappings among multiple domains using only a single generator and a discriminator, training effectively from images of all domains.   
- Jointly Training: Successfully learn multi-domain image translation between multiple datasets by utilizing a mask vector method that enables StarGAN to control all available domain labels.   
- StarGAN showed its superiority over
baseline models.


## Star Generative Adversarial Networks
- Multi-Domain Image-to-Image Translation:
  - Adversarial Loss:
  - Domain Classification Loss:
  - Reconstruction Loss:
  
  	$\rightarrow$ Full Objective:

- Training with Multiple Datasets

Issue: An issue when learning from multiple
datasets, however, is that the label information is only partially known to each dataset.

Solution:
  Mask Vector: We introduce a mask vector m that allows StarGAN to ignore unspecified labels and focus on the explicitly known label provided by a particular dataset.

## Implementation

- Improved GAN Training: To stabilize the training process
and generate higher quality images, we replace Adversarial Loss with Wasserstein GAN objective. 

- Network Architecture

## Experiments

1. Compare starGAN against recent methods   
   
2. Experiments on facial expression synthesis   
  
3. Results that starGAN can learn image-to-image translation from multiple datasets.

## Conclusion
Besides the advantages in scalability, StarGAN generated images of higher visual quality compared to existing methods, owing to the generalization capability behind the multi-task learning setting. In addition, the use of the proposed simple mask vector enables StarGAN to utilize multiple datasets
with different sets of domain labels, thus handling all available labels from them. 