# Step-by-step installation instructions

Following https://mmdetection3d.readthedocs.io/en/latest/getting_started.html#installation



**a. Create a conda virtual environment and activate it.**
```shell
conda create -n vox python=3.8 -y
conda activate vox
```

**b. Install PyTorch and torchvision following the [official instructions](https://pytorch.org/).**
```shell
pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html
# Recommended torch>=1.9
# verify:
python -c 'import torch;print(torch.__version__);print(torch.version.cuda)'

```

**c. Install gcc>=5 in conda env (optional).**
```shell
conda install -c omgarcia gcc-6 -y # gcc-6.2
```

**c. Install mmcv-full.**
```shell
#  pip install mmcv-full==1.4.0
#  pip install mmcv-full==1.4.0 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
pip install mmcv-full==1.3.9 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
```

**d. Install mmdet and mmseg.**
```shell
pip install mmdet==2.14.0
pip install mmsegmentation==0.14.1
```

**e. Install mmdet3d from source code.**
```shell
git clone https://github.com/open-mmlab/mmdetection3d.git
cd mmdetection3d
git checkout v0.17.1 # Other versions may not be compatible.
pip install -v -e .
cd ..
```

**f. Install timm.**
```shell
pip install timm
```


**g. Clone VoxFormer.**
```
git clone https://github.com/amit-eee/VoxFormer.git
```

**h. Prepare pretrained resnet50 models.**
```shell
cd VoxFormer && mkdir ckpts && cd ckpts
```
Download the pretrained [resnet50](https://drive.google.com/file/d/1A4Efx7OQ2KVokM1XTbZ6Lf2Q5P-srsyE/view?usp=share_link).


**i. Install einops and seaborn.**
```shell
pip install einops
pip install seaborn
```

**everything together**
```shell
conda create -n vox python=3.8 -y
conda activate vox
pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html
# Recommended torch>=1.9
# verify:
python -c 'import torch;print(torch.__version__);print(torch.version.cuda)'
conda install -c omgarcia gcc-6 -y# gcc-6.2
#  pip install mmcv-full==1.4.0
#  pip install mmcv-full==1.4.0 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
pip install mmcv-full==1.3.9 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
pip install mmdet==2.14.0
pip install mmsegmentation==0.14.1
git clone https://github.com/open-mmlab/mmdetection3d.git
cd mmdetection3d
git checkout v0.17.1 # Other versions may not be compatible.
pip install -v -e .
cd ..
pip install timm
git clone https://github.com/amit-eee/VoxFormer.git
cd VoxFormer && mkdir ckpts && cd ckpts
pip install einops
pip install seaborn


```
