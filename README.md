# AgriGPTs
Research and Development of Agricultural Large Models|农业大模型研究与开发

# AgriGPTs-农业大模型研究与开发


## AgriGPTs系列模型

- [AgriGPT-6B](https://huggingface.co/AgriGPTs/AgriGPT-6B)，此版本为学术demo版，基于[ChatGLM2-6B](https://github.com/THUDM/ChatGLM2-6B)训练而来,所需显存约13225MB/1024=12.91GB。

- [AgriGPT-13B](https://huggingface.co/AgriGPTs/AgriGPT-13B)，此版本为学术demo版，基于[Baichuan2-13B](https://github.com/baichuan-inc/Baichuan2-13B)训练而来所需显存约30425MB/1024=29.7GB。
- **注意：** AgriGPT-13B目前通过预训练已经丧失了对话能力，对话能力将在下一个版本进行增强和改进。

## 简介 Brief Introduction

在农业领域，随着人工智能的不断发展，大规模语言模型（LLM）在该领域的应用提供了更多机会。尽管医疗、教育和金融等领域已经逐渐形成了自己的模型，但是农业领域在这方面的进展较为滞后，目前没有针对农业领域的大模型。

为了推动LLM在农业甚至其他垂直领域的实际应用，本项目通过开源了第一个农业大模型，后续会开源更多的农业大模型，旨在促进开放性研究和技术落地。

## 数据 Dataset

我们的数据主要由百度百科，维基百科以及各种文本数据组成，随后经过清洗、数据增强等处理原始数据，形成持续预训练数据


## 实验结果 experiments

## 效果 Results

## 未来计划

本Demo只是一个开始，我们将致力于开发面向大众的产品，期待通过大模型助力农业领域的发展。

如果您有进一步了解产品、进行投资、商务合作的需求，请联系agrigpt@outlook.com

##  使用 Usage

```python
import torch
from transformers import AutoModelForCausalLM, AutoTokenizer
from transformers.generation.utils import GenerationConfig

model_HF_ID_or_path = "path_of_checkpoint_or_model_HF_ID"

tokenizer = AutoTokenizer.from_pretrained(model_HF_ID_or_path, use_fast=False,
                                          trust_remote_code=True)
model = AutoModelForCausalLM.from_pretrained(model_HF_ID_or_path, device_map="auto",
                                             torch_dtype=torch.bfloat16, trust_remote_code=True)
model.generation_config = GenerationConfig.from_pretrained(model_HF_ID_or_path)
messages = [{"role": "user", "content": "告诉我小麦作物会存在的所有病虫害有哪些"}]
response = model.chat(tokenizer, messages)
print(response)
```

欢迎引用我们:

```
@misc{AgriGPTs,
  author={Bolong Liu and Rongqiang Zhao and Jie Liu and Qiang Wang},
  title={AgriGPTs},
  year={2023},
  publisher={GitHub},
  journal={GitHub repository},
  howpublished={\url{https://github.com/AgriGPTs/AgriGPTs}},
}
```




## Star History

[![Star History](https://api.star-history.com/svg?repos=AgriGPTs/AgriGPTs&type=Date)](https://star-history.com/#AgriGPTs/AgriGPTs&Date)

## Contributors
<a href="https://github.com/bolongliu/bolongliu/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=bolongliu/bolongliu" />
</a>

<a href="https://github.com/AgriGPT/AgriGPT/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=AgriGPT/AgriGPT" />
</a>
