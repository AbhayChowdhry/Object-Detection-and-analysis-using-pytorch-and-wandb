# Object-Detection-and-analysis-using-pytorch-and-wandb

Experimented Object detection on Russian Wildlife dataset

### Labels

- Cyan : glittering-fireworks : Default Convolutional Neural Network (Resnet18) with no fine-tuning
- Green : sparkling-dog : Resnet18 (pretrained) is fine-tuned on the dataset with 0.0001 learning rate
- Yellow : glistening-lantern : Resnet18 (pretrained) is fine-tuned on the dataset with 0.001 learning rate
- Red : sweet-orchid : Augmented Data # 1 (Resize, ToTensor, Normalize, RandomRotation, RandomHorizontalFlip, ColorJitter)
- Blue : goldern-orchid : Augmented Data # 2 (Resize, ToTensor, Normalize, RandomRotation, RandomHorizontalFlip, GaussianBlur)

![alt text](https://github.com/AbhayChowdhry/Object-Detection-and-analysis-using-pytorch-and-wandb/blob/main/media/Training_acc.png)


![alt text](https://github.com/AbhayChowdhry/Object-Detection-and-analysis-using-pytorch-and-wandb/blob/main/media/Training_loss.png)


### Comprasison and Analysis

1. We clearly see that pretrained models outperformed the other ones
2. We see effect of a higher learning rate on the yellow graph which seems to suddenly drop in accuracy and increase in loss, which was cured by decreasing the learning rate, it seems that at this stage the model was overshooting the minima and hence the learning rate was decreased to get a better minima
3. We were not able to attain better results using data augmentation, this might be due to the fact that the data augmentation was not able to generate enough data to make the model generalize better
4. However, We see that the augmented data with gaussian blur (Red) is slightly outperforming the one where the guassian blur is replaced by RandomCrop, this might be due to the fact that the gaussian blur is able to generate more data which is closer to the original data and hence the model is able to generalize better

Hence, we can conclude that the best model is the one which is pretrained and fine-tuned with a learning rate of 0.0001


![alt text](https://github.com/AbhayChowdhry/Object-Detection-and-analysis-using-pytorch-and-wandb/blob/main/media/validation_acc.png)


![alt text](https://github.com/AbhayChowdhry/Object-Detection-and-analysis-using-pytorch-and-wandb/blob/main/media/validation_loss.png)
