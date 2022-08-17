# cellpose_GRIN_dendrite_models
Models trained on dendrites imaged through 2p GRIN
 
These are just models that can be used to segment out dendrites with [Cellpose](https://github.com/MouseLand/cellpose). 
Training set is a collection of 30 manually labeled images that have undergone [local normalization](https://github.com/xzhang03/Local-normalize).
This repo documents progress in this regard. 
 
## Samples (not in the training set)

### 0. Base image
![Base image](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/base.png).

### 1. Model from scratch
#### 100 Epochs
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model None --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
![GRINDen_Sc100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Sc100.png)

### 2. Retrained model from nuclei
#### 100 Epochs
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model nuclei --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
![GRINDen_Nu100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu100.png)

### 3. Retrained model from cyto
#### 100 Epochs
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model cyto --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
![GRINDen_Cy100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Cy100.png)
