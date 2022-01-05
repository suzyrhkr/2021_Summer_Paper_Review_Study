# StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation

<img width="601" alt="Screenshot 2022-01-05 at 10 25 02 AM" src="https://user-images.githubusercontent.com/48341349/148146039-935b4cbb-bed1-4438-ad05-bdfc0f77f54d.png">

## Abstract
Image -to-Image Translation:
existing approaches have limited scalability and robustness in handling more than two domains, since different models should be built independently for every pair of image domains.    
To address this limitation, we propose StarGAN, a novel and
scalable approach that can perform image-to-image translations for multiple domains using only a single model.

## Introduction
The task of image-to-image translation : To change a
particular aspect of a given image to another, e.g., changing the facial expression of a person from smiling to frowning.   

However, existing models are both inefficient and ineffective in such multi-domain image translation tasks.

<img width="427" alt="Screenshot 2022-01-04 at 4 43 55 PM" src="https://user-images.githubusercontent.com/48341349/148025706-b5d665df-8e45-4918-a6e0-46d2a0eb257b.png">

### Terms:
- attribute: a meaningful feature inherent in an image such as hair color, gender or age   
- attribute value: a particular value of an attribute, e.g.,
black/blond/brown for hair color or male/female for gender   
- domain: a set of images sharing the
same attribute value   

### Dataset:
- CelebA: s 40 labels related to facial attributes such as hair color, gender, and age   
- RaFD Dataset: 8 labels for facial expressions such as ‘happy’, ‘angry’ and ‘sad’

### Contributions:
-  Proposed StarGAN, a novel generative adversarial
network that learns the mappings among multiple domains using only a single generator and a discriminator, training effectively from images of all domains.   
- Jointly Training: Successfully learn multi-domain image translation between multiple datasets by utilizing a mask vector method that enables StarGAN to control all available domain labels.   
- StarGAN showed its superiority over baseline models.


## Star Generative Adversarial Networks
- Multi-Domain Image-to-Image Translation:
  - Adversarial Loss:    
    <img width="261" alt="Screenshot 2022-01-05 at 10 31 02 AM" src="https://user-images.githubusercontent.com/48341349/148146424-49180243-d87f-4d79-a7d9-c5f1dd9ad8ad.png">   

  - Domain Classification Loss:   
    <img width="172" alt="Screenshot 2022-01-04 at 4 46 22 PM" src="https://user-images.githubusercontent.com/48341349/148025978-98df18ff-e9ee-45b7-a09d-88cb61e3919b.png">.   
    <img width="188" alt="Screenshot 2022-01-04 at 4 46 49 PM" src="https://user-images.githubusercontent.com/48341349/148026017-5b667a15-4c73-4c9d-a54a-c206464d137d.png"> 
  - Reconstruction Loss:   
    <img width="201" alt="Screenshot 2022-01-05 at 10 26 20 AM" src="https://user-images.githubusercontent.com/48341349/148146132-ef5a93e2-a0d3-460f-b096-e103679abb0b.png">  
    
  	-> Full Objective:   
    <img width="199" alt="Screenshot 2022-01-04 at 4 47 19 PM" src="https://user-images.githubusercontent.com/48341349/148026070-c3e513df-9881-474f-9a9c-b23bf94cf38b.png">

- Training with Multiple Datasets

Issue: An issue when learning from multiple
datasets, however, is that the label information is only partially known to each dataset.

Solution:
  Mask Vector: We introduce a mask vector m that allows StarGAN to ignore unspecified labels and focus on the explicitly known label provided by a particular dataset.
<img width="115" alt="Screenshot 2022-01-04 at 4 51 49 PM" src="https://user-images.githubusercontent.com/48341349/148026546-048a6516-184b-4cd0-894e-a3a5412f80d8.png">

## Implementation

- Improved GAN Training: To stabilize the training process
and generate higher quality images, we replace Adversarial Loss with Wasserstein GAN objective. 

- Network Architecture: Refer to paper Table 4. and Table 5.
<img width="636" alt="Screenshot 2022-01-05 at 10 36 40 AM" src="https://user-images.githubusercontent.com/48341349/148146859-ff9ca36b-5b3e-4a69-bde3-ed59eb108165.png">

## Experiments

1. Compare starGAN against recent methods   
   <img width="363" alt="Screenshot 2022-01-04 at 4 52 45 PM" src="https://user-images.githubusercontent.com/48341349/148026660-649f90a3-5489-4ee9-a24b-e6bdf3877b61.png">

2. Experiments on facial expression synthesis   
<img width="635" alt="Screenshot 2022-01-04 at 4 53 38 PM" src="https://user-images.githubusercontent.com/48341349/148026788-04309688-ada6-4e7e-9c92-3b65bb044f09.png">

3. Results that starGAN can learn image-to-image translation from multiple datasets.
  <img width="638" alt="Screenshot 2022-01-04 at 4 54 01 PM" src="https://user-images.githubusercontent.com/48341349/148026842-7518fb0f-3296-4c37-8abd-783d9098a813.png">

## Conclusion
Besides the advantages in scalability, StarGAN generated images of higher visual quality compared to existing methods, owing to the generalization capability behind the multi-task learning setting.   
In addition, the use of the proposed simple mask vector enables StarGAN to utilize multiple datasets with different sets of domain labels, thus handling all available labels from them. 
