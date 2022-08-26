# cellpose_GRIN_dendrite_models
Models trained on dendrites imaged through 2p GRIN
 
These are just models that can be used to segment out dendrites with [Cellpose](https://github.com/MouseLand/cellpose). 
Training set is a collection of 30 manually labeled images that have undergone [local normalization](https://github.com/xzhang03/Local-normalize).
This repo documents progress in this regard. 

Lens: NEM-050-25-10-860-DM
Objective: NIKON CFI PLAN APO LAMBDA 4X OBJECTIVE
 
## Samples (not in the training set)

### 0. Base image
1. [Base image](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/base.png).
2. [Base image axons](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/base_axon.png).

### 1. Retrained model from nuclei
#### 100 Epochs (trained with a 31-image training set A)
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model nuclei --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
1. [GRINDen_Nu100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu100.png)
2. [GRINDen_Nu100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu100_axons.png)
#### 500 Epochs (trained with a 31-image training set A)
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model nuclei --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 500 --verbose
1. [GRINDen_Nu500](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu500.png)
#### 2000 Epochs (further refined with a 119-image training set B)
>python -m cellpose --train --dir ~/cellpose/training_full2 --pretrained_model nuclei --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 2000 --verbose
1. [GRINDen_Nu2000](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu2000.png)
2. [GRINDen_Nu2000](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Nu2000_axons.png)

### 2. Retrained model from cyto
#### 100 Epochs (trained with a 31-image training set A)
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model cyto --diameter 10 --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
1. [GRINDen_Cy100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Cy100.png)
2. [GRINDen_Cy100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Cy100_axons.png)

### Retired 1. Model from scratch (retired)
#### 100 Epochs (trained with a 31-image training set A)
>python -m cellpose --train --dir ~/cellpose/training_full --pretrained_model None --mask_filter _seg.npy --chan 0 --chan2 0 --learning_rate 0.1 --weight_decay 0.0001 --n_epochs 100 --verbose
1. [GRINDen_Sc100](https://github.com/xzhang03/cellpose_GRIN_dendrite_models/blob/main/sample_images/GRINDen_Sc100.png)
