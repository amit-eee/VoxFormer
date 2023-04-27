# Prerequisites

**Please ensure you have prepared the environment and the SemanticKITTI dataset.**

# Train and Test

## Stage-1: Class-Agnostic Query Proposal
Train QPN with 4 GPUs 
```
CUDA_VISIBLE_DEVICES=1,2,3,4 bash ./tools/dist_train.sh ./projects/configs/voxformer/qpn.py 4
```

Eval QPN with 4 GPUs
```
CUDA_VISIBLE_DEVICES=1,2,3,4 bash ./tools/dist_test.sh ./projects/configs/voxformer/qpn.py ckpts/resnet50-19c8e357.pth 4
```
## Stage-2: Class-Specific Voxel Segmentation
Train VoxFormer with temporal information with 4 GPUs 
```
CUDA_VISIBLE_DEVICES=1,2,3,4 bash ./tools/dist_train.sh ./projects/configs/voxformer/voxformer-T.py 4
```

Eval VoxFormer with temporal information with 4 GPUs
```
CUDA_VISIBLE_DEVICES=1,2,3,4 bash ./tools/dist_test.sh ./projects/configs/voxformer/voxformer-T.py ckpts/miou13.35_iou44.15_epoch_12.pth 4
```
