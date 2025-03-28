# pianos
[![license](https://img.shields.io/github/license/monetjoe/pianos.svg)](https://github.com/monetjoe/pianos/blob/master/LICENSE)
[![Python application](https://github.com/monetjoe/pianos/actions/workflows/python-app.yml/badge.svg?branch=main)](https://github.com/monetjoe/pianos/actions/workflows/python-app.yml)
[![hf](https://img.shields.io/badge/HuggingFace-pianos-ffd21e.svg)](https://huggingface.co/collections/monetjoe/pianos-67e39971c0749958f63b2b7c)
[![ms](https://img.shields.io/badge/ModelScope-pianos-624aff.svg)](https://www.modelscope.cn/collections/pianos-a1856d7f57284c)
[![arxiv](https://img.shields.io/badge/arXiv-2310.04722-b31b1b.svg)](https://arxiv.org/pdf/2310.04722.pdf)
[![csmt](https://img.shields.io/badge/DOI-10.1007/978--981--97--7962--8__1-001447.svg)](https://doi.org/10.1007/978-981-97-7962-8_1)

Classify piano sound quality by fine-tuned pre-trained CNN models.

## Requirements
```bash
conda create -n py311 python=3.11 -y
conda activate py311
pip install -r requirements.txt
```

## Usage
### Maintenance
```bash
git clone git@github.com:monetjoe/pianos.git
cd pianos
```

### Train
Assign a backbone(take squeezenet1_1 as an example) after `--model` to start training:
```bash
python train.py --model squeezenet1_1 --fullfinetune True --wce True
```
`--fullfinetune True` means full finetune, `False` means linear probing<br>
`--wce True` means using focal loss

#### Supported backbones
| <a href="https://huggingface.co/datasets/monetjoe/cv_backbones" target="_blank">Mirror 1</a> | <a href="https://www.modelscope.cn/datasets/monetjoe/cv_backbones/dataPeview" target="_blank">Mirror 2</a> |
| :------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------: |

### Plot results
After finishing the training, use the below command to plot the latest results:
```bash
python plot.py
```

## Results
A demo result of SqueezeNet fine-tuning:
|             Results              |                                        Plots                                         |
| :------------------------------: | :----------------------------------------------------------------------------------: |
|            Loss curve            | ![](https://github.com/user-attachments/assets/f6893fdd-9315-44c7-850f-6a29ebdc8c15) |
| Training and validation accuracy | ![](https://github.com/user-attachments/assets/07c7fb83-156c-40f8-9372-f96a818eeb39) |
|         Confusion matrix         | ![](https://github.com/user-attachments/assets/284b82e5-bb45-44f1-8bdc-7d2832d3e6c3) |

## Cite
```bibtex
@inproceedings{zhou2023holistic,
  title        = {A holistic evaluation of piano sound quality},
  author       = {Monan Zhou and Shangda Wu and Shaohua Ji and Zijin Li and Wei Li},
  booktitle    = {National Conference on Sound and Music Technology},
  pages        = {3-17},
  year         = {2023},
  organization = {Springer}
}
```
