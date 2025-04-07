# BacktrackingCorrection
## Introduction:
The code and data for *Training Large Language Models for Retrieval-Augmented Question Answering through Backtracking Correction* (ICLR2025).
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
Some packages are not consistent with the original repo. You must follow the instructions listed above.

## Data position:
Our data is available in repo: https://huggingface.co/HuggingMicah/BackTrackingDataset.

Files prefixed with `llama2_chat_template` are utilized for fine-tuning the Llama 2 model, where the `instruction` field follows the system prompt style of the Llama 2 model. Similarly, files prefixed with `llama3_chat_template` serve the same purpose for fine-tuning Llama 3, adhering to its system prompt style.  

The `step` in the filenames denotes the corresponding step in the document decision tree. For instance, `step1` signifies the preparation to explain the first document, `step2` corresponds to the second document, and this pattern continues for subsequent steps.  

Field explanations:  
- **instruction**: Represents the input used during the training process.  
- **chosen_output**: Contains positive response (desired output).  
- **rejected_output**: Contains negative response (undesired output).  
- **source**: Indicates the origin or source of the question.

