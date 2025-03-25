# BacktrackingCorrection

## Create environments:
We conduct training based on alignment-handbook:
```shell
git clone https://github.com/huggingface/alignment-handbook
```
Then we need to create the environment for training:
```shell
conda create -n train python=3.10 -y
conda activate train
pip install torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 --index-url https://download.pytorch.org/whl/cu121
cd alignment-handbook
python -m pip install .
pip install trl==0.12.0
pip install numpy==1.26.4
wget https://github.com/Dao-AILab/flash-attention/releases/download/v2.7.4.post1/flash_attn-2.7.4.post1+cu12torch2.2cxx11abiFALSE-cp310-cp310-linux_x86_64.whl
pip install flash_attn-2.7.4.post1+cu12torch2.2cxx11abiFALSE-cp310-cp310-linux_x86_64.whl
```
### Notice:
Some packages are not consistent with the original repo.

## Data position:
Our data is available in this repo.
