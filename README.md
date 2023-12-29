# Deita

<p align="center">
  <img src="./assets/logo-final.png" width="600">
</p>

<p align="center">
  :hugs: <a href="https://huggingface.co/collections/hkust-nlp/deita-6569c198c174808d94cf5bd4">HF Repo</a>&nbsp;&nbsp;&nbsp;
  :page_with_curl: <a href="https://arxiv.org/abs/2312.15685">Paper</a>
</p>

Welcome to Deita (**D**ata-**E**fficient **I**nstruction **T**uning for **A**lignment) Project! 

This is the **preview version** of Deita. We will continue to update, please stay tuned!


## What is Deita?
Deita is an open-sourced project designed to facilitate **Automatic Data Selection** for instruction tuning in Large Language Models (LLMs).

It includes:
- **Open-sourced Toolkits** for automatic data selection in instruction tuning
- **Deita Datasets**: A series of extremely *lightweight*, high-quality alignment SFT data. We release 6k-sized and 10k-sized datasets in the first release
- **Deita Models**: A series of powerful models on par with SOTA chat LLMs with an extremely efficient instruction tuning Process. Deita models can be obtained by training with 10x less instruction tuning data compared with other SOTA LLMs

## News

- :fire: [12/2023] We release the first collection of the Deita resources [here](https://huggingface.co/collections/hkust-nlp/deita-6569c198c174808d94cf5bd4), which include a series of extremely lightweight, effective sft datasets, the data complexity/quality scorer models, as well as the resulted deita chat models. 

## Performance
:bell: Still curious about how far a small amount of high-quality data can lead LLMs? 

Deita may provide an answer for you:

**🔦 Highlights**
| Model                                          | Align        | Data Size  | MT-Bench | AlpacaEval(%) |
|------------------------------------------------|--------------|------------|----------|---------------|
| Zephyr-7B-sft                                  | SFT          | 200K       | 5.32     | 75.12         |
| $\text{Zephyr-7B-}\beta$                      | SFT + DPO    | 200K SFT + 60K DPO | 7.34     | 90.60         |
| OpenChat-3.5                                   | C-RLFT | >> 70K C-RLFT | 7.81     | 88.51         |
| Starling-7B                                    | C-RLFT + APA | >> 70K C-RLFT + 183K APA | 8.09     | 91.99         |
| Tulu-2-13B                                     | SFT          | 326K       | 6.70     | 78.90         |
| Tulu-2-13B+DPO                                 | SFT + DPO    | 326K SFT + 60K DPO | 7.00     | 89.50         |
| LLaMA2-13B-Chat                                | SFT + PPO    | --         | 6.65     | 81.09         |
| WizardLM-13B-v1.2                              | SFT          | >70K       | 7.09     | 89.17         |
| Vicuna-13B-v1.5                                | SFT          | >125K      | 6.57    | 78.80         |
| DEITA-7B-v1.0 (6K)          | SFT          | 6K       |   7.22   |    80.78      |
| DEITA-7B-v1.0-sft            | SFT          | 10K        | 7.32     | 81.67         |
| DEITA-7B-v1.0 | SFT + DPO    | 6K SFT + 10K DPO | 7.55     | 90.06         |

DEITA models are based on Mistral-7B-v0.1. :fire: 

Please refer to [this table](#chart\_with\_upwards\_trend-full-evaluations) for full evaluations including Open LLM Leaderboard as well, which includes DEITA models with LLaMA base models and comparisons with other data selection approaches.



## :chart_with_upwards_trend: Full Evaluations

<details>
  <summary>See full evaluations</summary>

| Model                                          | Align     | Data Size  | MT-Bench | AlpacaEval(%) | OpenLLM (Avg.) |
|------------------------------------------------|-----------|------------|----------|---------------|----------------|
| **Proprietary Models**                         |           |            |          |               |                |
| GPT-4-Turbo                                    | ?         | --         | 9.32     | 97.70         | --             |
| GPT-4                                          | SFT + PPO | --         | 8.99     | 95.03         | --             |
| Claude-2                                       | SFT + PPO | --         | 8.06     | 91.36         | --             |
| GPT-3.5-turbo                                  | SFT + PPO | --         | 7.94     | 89.37         | --             |
| **Open-sourced Models based on LLaMA-1-13B**   |           |            |          |               |                |
| LIMA                                           | SFT       | 1K SFT        | 4.29     | 41.98         | 59.82          |
| WizardLM-13B                                   | SFT       | 70K SFT       | 6.35     | 75.31         | 58.96          |
| Vicuna-13B-v1.3                                | SFT       | 125K SFT      | 6.39     | 82.11         | 60.01          |
| Random                                         | SFT       | 10K SFT       | 6.03     | 71.52         | 60.14          |
| DEITA-LLaMA1-13B-v1.0-sft                           | SFT       | 10K SFT       | 6.60     | 78.01         | 64.27          |
| **Open-sourced Models based on LLaMA-2-13B**   |           |            |          |               |                |
| Tulu-2-13B                                     | SFT       | 326K SFT      | 6.70     | 78.90         | --             |
| Tulu-2-13B+DPO                                 | SFT + DPO | 326K SFT + 60K DPO | 7.00     | 89.50         | --             |
| LLaMA2-13B-Chat                                | SFT + PPO | --         | 6.65     | 81.09         | --             |
| WizardLM-13B-v1.2                              | SFT          | >70K SFT      | 7.09     | 89.17         | --             |
| Vicuna-13B-v1.5                                | SFT       | 125K SFT      | 6.57     | 78.80         | 61.63          |
| Random                                         | SFT       | 10K SFT       | 5.78     | 65.19         | 61.32          |
| DEITA-LLaMA2-13B-v1.0-sft                           | SFT       | 10K SFT       | 6.79     | 81.09         | 62.71          |
| **Open-sourced Models based on Mistral-7B**    |           |            |          |               |                |
| Mistral-7B-Instruct-v0.1                       | --        | --         | 6.84     | 69.65         | 60.45          |
| Zephyr-7B-sft                                  | SFT       | 200K SFT      | 5.32     | 75.12         | 60.93          |
| $\text{Zephyr-7B-}\beta$                       | SFT + DPO | 200K SFT + 60K DPO | 7.34     | 90.60         | 66.36          |
| OpenChat-3.5                                   | C-RLFT | >> 70K C-RLFT | 7.81     | 88.51         | --           |
| Starling-7B                                    | C-RLFT + APA | >>70K C-RLFT + 183K APA | 8.09     | 91.99         | --            |
| Random                                         | SFT       | 10K SFT       | 5.89     | 56.90         | 61.72          |
| DEITA-7B-v1.0-sft (6K)                           | SFT       | 6K SFT       | 7.22     | 80.78         | 64.94          |
| DEITA-7B-v1.0-sft (10K)                  | SFT       | 10K SFT       | 7.32     | 81.67         | 64.00          |
| DEITA-7B-v1.0             | SFT + DPO | 6K SFT + 10K DPO   | 7.55     | 90.06         | 69.86          |


</details>

## :rocket: Deita Resources

| Resource                                       | Link     | License  |
|------------------------------------------------|-----------|------------|
| **Deita Datasets**                                   |           |            |
| deita-6k-v0                                    | [:hugs: HF Repo](https://huggingface.co/datasets/hkust-nlp/deita-6k-v0)          | [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) |
| deita-10k-v0                                    | [:hugs: HF Repo](https://huggingface.co/datasets/hkust-nlp/deita-10k-v0)          | [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) |
| **Scorers**                                   |           |             |
|  deita-complexity-scorer                      | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-complexity-scorer)          | [LLaMA License](https://ai.meta.com/resources/models-and-libraries/llama-downloads/)|
|  deita-quality-scorer               | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-quality-scorer)          | [LLaMA License](https://ai.meta.com/resources/models-and-libraries/llama-downloads/)|
| **Deita Models**                                   |           |             |
| DEITA-7B-v1.0-sft                | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-7b-v1.0-sft)           | [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)             |
| DEITA-7B-v1.0                | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-7B-v1.0)           | [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0)             |
| DEITA-LLaMA2-13B-v1.0-sft         | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-llama2-13b-v1.0-sft)           |  [LLaMA 2 License](https://ai.meta.com/resources/models-and-libraries/llama-downloads/)           |
| DEITA-LLaMA1-13B-v1.0-sft          | [:hugs: HF Repo](https://huggingface.co/hkust-nlp/deita-llama1-13b-v1.0-sft)          |  [LLaMA License](https://ai.meta.com/resources/models-and-libraries/llama-downloads/)           |

## :running_man: How to start?


### Installation
```bash
  git clone https://github.com/hkust-nlp/deita.git
  cd deita
  pip install -e .
```

### Data Sample Scoring

If you wish to assess the **quality** of a response for a single sample, you can follow these steps:
```python
from deita.selection.scorer import Llama_Scorer

model_name_or_path = "hkust-nlp/deita-quality-scorer"

scorer = Llama_Scorer(model_name_or_path)

# example input
input_text = "word to describe UI with helpful tooltips" # Example Input
output_text = "User-friendly or intuitive UI" # Example Output
quality_score = scorer.infer_quality(input_text, output_text)

print(quality_score)
# 2.0230105920381902
```

Deita also supports VLLM for faster inference. If you want to use VLLM for inference,

```bash
pip install vllm
```

And set ```is_vllm = True``` when initilizing scorer

```python
scorer = Llama_Scorer(model_name_or_path, is_vllm = True)
```

To assess other dimensions of data samples, please refer to the ```examples/scoring```

### SFT Training
Please refer to ```examples/train/sft.sh```
```bash
deepspeed --include localhost:${DEVICES} --master_port 29501 src/deita/alignment/train.py \
    --model_name_or_path ${MODELPATH} \
    --data_path ${DATAPATH} \
    --output_dir ${OUTPUTPATH}/${RUNNAME} \
    --num_train_epochs 6 \
    --per_device_train_batch_size ${BSZPERDEV} \
    --per_device_eval_batch_size 1 \
    --gradient_accumulation_steps ${GRADACC} \
    --eval_steps 50 \
    --save_strategy "no" \
    --save_steps 100 \
    --save_total_limit 10 \
    --learning_rate 2e-5 \
    --warmup_ratio 0.1 \
    --lr_scheduler_type "cosine" \
    --logging_steps 1 \
    --do_eval False \
    --evaluation_strategy "no" \
    --model_max_length 2048 \
    --lazy_preprocess True \
    --conv_template "vicuna_v1.1" \
    --mask_user True \
    --report_to "wandb" \
    --run_name ${RUNNAME} \
    --bf16 True \
    --deepspeed src/deita/ds_configs/deepspeed_config_zero2_no_offload.json
```

### DPO Training
Please refer to ```examples/train/dpo.sh```
```bash
deepspeed --include localhost:${DEVICES} --master_port 29502 src/deita/alignment/dpo_train.py \
    --model_name_or_path ${MODELPATH} \
    --json_path ${JSONPATH} \
    --data_split ${DATASPLIT} \
    --output_dir ${OUTPUTPATH}/${RUNNAME} \
    --num_train_epochs ${DPOEPOCH} \
    --beta 0.1 \
    --per_device_train_batch_size ${BSZPERDEV} \
    --per_device_eval_batch_size 1 \
    --gradient_accumulation_steps ${GRADACC} \
    --save_global_steps False \
    --eval_steps 50 \
    --save_strategy "no" \
    --save_steps 500 \
    --save_total_limit 1 \
    --learning_rate 5e-7 \
    --warmup_ratio 0.1 \
    --lr_scheduler_type "linear" \
    --logging_steps 1 \
    --do_eval False \
    --evaluation_strategy "no" \
    --model_max_length 2048 \
    --conv_template "vicuna_v1.1" \
    --report_to "wandb" \
    --run_name ${RUNNAME} \
    --bf16 True \
    --gradient_checkpointing True \
    --deepspeed src/deita/ds_configs/stage3_no_offloading_accelerate.json
```

### Evaluation
- For MT-Bench, please refer to [MT-Bench](https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge)
- For AlpacaEval, please refer to [alpaca_eval](https://github.com/tatsu-lab/alpaca_eval)
- For Open LLM Benchmark, please refer to [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness/tree/master) and follow settings on [HuggingFaceH4/open_llm_leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard)

## :muscle: What's more?

This is the preview version of Deita project. We will continue to update including

- [ ] Release data selection pipeline with efficient implementation
- [ ] More automatic data selection strategies
- [ ] CLI-Interface Supported
- [ ] Online Demo

## Citation
If you find the content of this project helpful, please cite our paper as follows:

```
@misc{liu2023what,
      title={What Makes Good Data for Alignment? A Comprehensive Study of Automatic Data Selection in Instruction Tuning}, 
      author={Wei Liu and Weihao Zeng and Keqing He and Yong Jiang and Junxian He},
      year={2023},
      eprint={2312.15685},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

## Acknowledgement
For training code, we use the code template of [fastchat](https://github.com/lm-sys/FastChat).
