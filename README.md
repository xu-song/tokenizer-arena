---
title: Tokenizer Arena
emoji: ⚡
colorFrom: red
colorTo: gray
sdk: gradio
sdk_version: 3.41.2
app_file: app.py
pinned: false
---



## 压缩率 Compress Rate


在 [cc-100](https://huggingface.co/datasets/cc100) 数据集，每个语言取1万条数据，测试不同tokenizer的压缩率。

> 压缩率示例：
llama3扩充了词典，具有更高的压缩比。同样1T字节的简体中文语料，llama分词后是 0.56万亿个token，llama3只需要0.31万亿个token。

| tokenizer                    |   vocab_size |    t_bytes/t_tokens |   t_tokens/t_bytes |   n_chars/n_tokens |
|:-----------------------------|-------------:|-------------------:|-------------------:|-------------------:|
| llama                        |        32000 |               1.8  |               0.56 |               0.7  |
| llama3                       |       128000 |               3.2  |               0.31 |               1.24 |

可通过以下脚本进行复现 
```sh
python utils/compress_rate_util.py 
```




<details> <summary>英文压缩率</summary>
在英文数据集 cc100-en 计算压缩率 

| tokenizer                   |   vocab_size |   g_bytes/b_tokens |   b_tokens/g_bytes |   t_bytes/t_tokens |   t_tokens/t_bytes |   n_chars/n_tokens |
|:----------------------------|-------------:|-------------------:|-------------------:|-------------------:|-------------------:|-------------------:|
| amber                       |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| aya_101                     |       250100 |               3.3  |               0.3  |               3.22 |               0.31 |               3.53 |
| baichuan                    |        64000 |               3.74 |               0.27 |               3.65 |               0.27 |               4    |
| baichuan2                   |       125696 |               3.89 |               0.26 |               3.8  |               0.26 |               4.17 |
| bert_base_cased             |        28996 |               3.64 |               0.27 |               3.55 |               0.28 |               3.89 |
| bert_base_chinese           |        21128 |               2.78 |               0.36 |               2.71 |               0.37 |               2.97 |
| bert_base_uncased           |        30522 |               3.73 |               0.27 |               3.65 |               0.27 |               4    |
| bloom                       |       250680 |               4.07 |               0.25 |               3.97 |               0.25 |               4.36 |
| byt5_small                  |          256 |               0.92 |               1.08 |               0.9  |               1.11 |               0.99 |
| character_glm_6b            |        64794 |               3.62 |               0.28 |               3.54 |               0.28 |               3.88 |
| chatglm2_6b                 |        64794 |               3.62 |               0.28 |               3.54 |               0.28 |               3.88 |
| chatglm3_6b                 |        64798 |               3.62 |               0.28 |               3.54 |               0.28 |               3.88 |
| chatglm_6b                  |       150344 |               3.68 |               0.27 |               3.59 |               0.28 |               3.94 |
| chatyuan_large_v2           |        32128 |               1.95 |               0.51 |               1.91 |               0.52 |               2.09 |
| chinese_llama               |        49953 |               3.59 |               0.28 |               3.51 |               0.28 |               3.85 |
| chinese_llama2              |        55296 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| code_davinci_002            |        50281 |               4.05 |               0.25 |               3.96 |               0.25 |               4.34 |
| crystal_coder               |        32000 |               3.68 |               0.27 |               3.59 |               0.28 |               3.94 |
| dbrx_instruct               |       100277 |               4.11 |               0.24 |               4.01 |               0.25 |               4.4  |
| deepseek_coder_33b_instruct |        32000 |               3.64 |               0.27 |               3.56 |               0.28 |               3.9  |
| deepseek_llm_7b_base        |       100000 |               3.85 |               0.26 |               3.76 |               0.27 |               4.12 |
| falcon_180b                 |        65024 |               3.99 |               0.25 |               3.9  |               0.26 |               4.27 |
| falcon_7b                   |        65024 |               3.99 |               0.25 |               3.9  |               0.26 |               4.27 |
| fastchat_t5_3b              |        32000 |               2.16 |               0.46 |               2.11 |               0.47 |               2.31 |
| flan_t5_base                |        32100 |               3.61 |               0.28 |               3.53 |               0.28 |               3.87 |
| gemma_7b                    |       256000 |               3.91 |               0.26 |               3.82 |               0.26 |               4.18 |
| gpt2                        |        50257 |               4.05 |               0.25 |               3.96 |               0.25 |               4.34 |
| gpt2_chinese                |        21128 |               2.67 |               0.37 |               2.61 |               0.38 |               2.86 |
| gpt_35_turbo                |       100277 |               4.11 |               0.24 |               4.01 |               0.25 |               4.4  |
| gpt_4                       |       100277 |               4.11 |               0.24 |               4.01 |               0.25 |               4.4  |
| gpt_nexo_20b                |        50254 |               4.04 |               0.25 |               3.94 |               0.25 |               4.32 |
| grok_1                      |       131072 |               4.06 |               0.25 |               3.96 |               0.25 |               4.35 |
| internlm2_chat_7b           |        92544 |               3.86 |               0.26 |               3.77 |               0.27 |               4.13 |
| internlm2_math_7b           |        92544 |               3.86 |               0.26 |               3.77 |               0.27 |               4.13 |
| internlm_chat_7b            |       103168 |               3.86 |               0.26 |               3.77 |               0.27 |               4.13 |
| internlm_xcomposer_7b       |       103168 |               3.86 |               0.26 |               3.77 |               0.27 |               4.13 |
| jamba_v0_1                  |        65536 |               3.82 |               0.26 |               3.73 |               0.27 |               4.09 |
| kplug                       |        10261 |               2.66 |               0.38 |               2.6  |               0.38 |               2.85 |
| llama                       |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| llama2                      |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| llama3                      |       128000 |               4.11 |               0.24 |               4.01 |               0.25 |               4.4  |
| mistral_7b                  |        32000 |               3.67 |               0.27 |               3.58 |               0.28 |               3.92 |
| mixtral_8_7b                |        32000 |               3.67 |               0.27 |               3.58 |               0.28 |               3.92 |
| mobilebert_uncased          |        30522 |               3.73 |               0.27 |               3.65 |               0.27 |               4    |
| moss                        |       106029 |               4.08 |               0.25 |               3.98 |               0.25 |               4.36 |
| mt5_large                   |       250100 |               3.3  |               0.3  |               3.22 |               0.31 |               3.53 |
| olmo_7b                     |        50280 |               4.04 |               0.25 |               3.94 |               0.25 |               4.32 |
| orion_14b_chat              |        84608 |               3.94 |               0.25 |               3.85 |               0.26 |               4.22 |
| phi_1                       |        50257 |               4.05 |               0.25 |               3.96 |               0.25 |               4.34 |
| phi_2                       |        50257 |               4.05 |               0.25 |               3.96 |               0.25 |               4.34 |
| pko_t5_large                |        50258 |               1.59 |               0.63 |               1.55 |               0.64 |               1.7  |
| prompt_clue                 |        32128 |               1.95 |               0.51 |               1.91 |               0.52 |               2.09 |
| qwen1_5_14b_chat            |       151643 |               4.06 |               0.25 |               3.97 |               0.25 |               4.35 |
| qwen_1_8b_chat              |       151851 |               4.06 |               0.25 |               3.97 |               0.25 |               4.35 |
| qwen_72b_chat               |       151851 |               4.06 |               0.25 |               3.97 |               0.25 |               4.35 |
| qwen_7b_chat                |       151851 |               4.06 |               0.25 |               3.97 |               0.25 |               4.35 |
| roberta_chinese_clue        |         8021 |               1.8  |               0.56 |               1.75 |               0.57 |               1.92 |
| skywork_13b_base            |        65519 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| skywork_13b_math            |        65519 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| solar_10_7b                 |        32000 |               3.67 |               0.27 |               3.58 |               0.28 |               3.92 |
| starchat_alpha              |        49152 |               3.63 |               0.28 |               3.54 |               0.28 |               3.88 |
| switch_c_2048               |        32100 |               3.61 |               0.28 |               3.53 |               0.28 |               3.87 |
| t5_base                     |        32100 |               3.61 |               0.28 |               3.53 |               0.28 |               3.87 |
| t5_large                    |        32100 |               3.61 |               0.28 |               3.53 |               0.28 |               3.87 |
| t5_small                    |        32100 |               3.61 |               0.28 |               3.53 |               0.28 |               3.87 |
| text_davinci_003            |        50281 |               4.05 |               0.25 |               3.96 |               0.25 |               4.34 |
| tigerbot_13b_chat_v2        |        60512 |               3.67 |               0.27 |               3.58 |               0.28 |               3.93 |
| tigerbot_70b_chat_v4_4k     |        65107 |               3.65 |               0.27 |               3.57 |               0.28 |               3.91 |
| wizardcoder_15b_v1          |        49152 |               3.63 |               0.28 |               3.54 |               0.28 |               3.88 |
| wizardcoder_python_7b_v1    |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| wizardlm_7b_v1              |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| wizardmath_70b_v1           |        32000 |               3.56 |               0.28 |               3.47 |               0.29 |               3.81 |
| xlm_roberta                 |       250002 |               3.49 |               0.29 |               3.41 |               0.29 |               3.74 |
| yi_34b                      |        64000 |               3.87 |               0.26 |               3.78 |               0.26 |               4.15 |
| yi_6b                       |        64000 |               3.87 |               0.26 |               3.78 |               0.26 |               4.15 |
| yi_vl34b                    |        64000 |               3.88 |               0.26 |               3.79 |               0.26 |               4.16 |
| zephyr_7b_beta              |        32000 |               3.67 |               0.27 |               3.58 |               0.28 |               3.92 |

</details>


<details> <summary>简体中文压缩率</summary>
在简体中文数据集 cc100-zh-Hans 计算压缩率 

| tokenizer                   |   vocab_size |   g_bytes/b_tokens |   b_tokens/g_bytes |   t_bytes/t_tokens |   t_tokens/t_bytes |   n_chars/n_tokens |
|:----------------------------|-------------:|-------------------:|-------------------:|-------------------:|-------------------:|-------------------:|
| amber                       |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| aya_101                     |       250100 |               3.89 |               0.26 |               3.79 |               0.26 |               1.47 |
| baichuan                    |        64000 |               3.92 |               0.26 |               3.82 |               0.26 |               1.48 |
| baichuan2                   |       125696 |               4.53 |               0.22 |               4.42 |               0.23 |               1.71 |
| bert_base_cased             |        28996 |               2.73 |               0.37 |               2.66 |               0.38 |               1.03 |
| bert_base_chinese           |        21128 |               2.74 |               0.37 |               2.67 |               0.37 |               1.03 |
| bert_base_uncased           |        30522 |               2.73 |               0.37 |               2.67 |               0.38 |               1.03 |
| bloom                       |       250680 |               4.28 |               0.23 |               4.18 |               0.24 |               1.62 |
| byt5_small                  |          256 |               0.93 |               1.08 |               0.91 |               1.1  |               0.35 |
| character_glm_6b            |        64794 |               4.2  |               0.24 |               4.1  |               0.24 |               1.59 |
| chatglm2_6b                 |        64794 |               4.2  |               0.24 |               4.1  |               0.24 |               1.59 |
| chatglm3_6b                 |        64798 |               4.2  |               0.24 |               4.1  |               0.24 |               1.59 |
| chatglm_6b                  |       150344 |               4.65 |               0.22 |               4.54 |               0.22 |               1.76 |
| chatyuan_large_v2           |        32128 |               4.34 |               0.23 |               4.24 |               0.24 |               1.64 |
| chinese_llama               |        49953 |               3.93 |               0.25 |               3.84 |               0.26 |               1.49 |
| chinese_llama2              |        55296 |               3.92 |               0.26 |               3.83 |               0.26 |               1.48 |
| code_davinci_002            |        50281 |               1.31 |               0.77 |               1.28 |               0.78 |               0.49 |
| crystal_coder               |        32000 |               1.86 |               0.54 |               1.81 |               0.55 |               0.7  |
| dbrx_instruct               |       100277 |               2.26 |               0.44 |               2.21 |               0.45 |               0.85 |
| deepseek_coder_33b_instruct |        32000 |               3.4  |               0.29 |               3.32 |               0.3  |               1.29 |
| deepseek_llm_7b_base        |       100000 |               4.05 |               0.25 |               3.96 |               0.25 |               1.53 |
| falcon_180b                 |        65024 |               2.18 |               0.46 |               2.13 |               0.47 |               0.82 |
| falcon_7b                   |        65024 |               2.18 |               0.46 |               2.13 |               0.47 |               0.82 |
| fastchat_t5_3b              |        32000 |              13.7  |               0.07 |              13.38 |               0.07 |               5.18 |
| flan_t5_base                |        32100 |              14.13 |               0.07 |              13.8  |               0.07 |               5.34 |
| gemma_7b                    |       256000 |               3.82 |               0.26 |               3.73 |               0.27 |               1.44 |
| gpt2                        |        50257 |               1.31 |               0.77 |               1.28 |               0.78 |               0.49 |
| gpt2_chinese                |        21128 |               2.73 |               0.37 |               2.66 |               0.38 |               1.03 |
| gpt_35_turbo                |       100277 |               2.26 |               0.44 |               2.21 |               0.45 |               0.85 |
| gpt_4                       |       100277 |               2.26 |               0.44 |               2.21 |               0.45 |               0.85 |
| gpt_nexo_20b                |        50254 |               2.01 |               0.5  |               1.96 |               0.51 |               0.76 |
| grok_1                      |       131072 |               1.73 |               0.58 |               1.69 |               0.59 |               0.66 |
| internlm2_chat_7b           |        92544 |               4.23 |               0.24 |               4.13 |               0.24 |               1.6  |
| internlm2_math_7b           |        92544 |               4.23 |               0.24 |               4.13 |               0.24 |               1.6  |
| internlm_chat_7b            |       103168 |               4.23 |               0.24 |               4.14 |               0.24 |               1.6  |
| internlm_xcomposer_7b       |       103168 |               4.23 |               0.24 |               4.14 |               0.24 |               1.6  |
| jamba_v0_1                  |        65536 |               2.3  |               0.44 |               2.24 |               0.45 |               0.87 |
| kplug                       |        10261 |               2.72 |               0.37 |               2.65 |               0.38 |               1.03 |
| llama                       |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| llama2                      |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| llama3                      |       128000 |               3.28 |               0.3  |               3.2  |               0.31 |               1.24 |
| mistral_7b                  |        32000 |               2.36 |               0.42 |               2.3  |               0.43 |               0.89 |
| mixtral_8_7b                |        32000 |               2.36 |               0.42 |               2.3  |               0.43 |               0.89 |
| mobilebert_uncased          |        30522 |               2.73 |               0.37 |               2.67 |               0.38 |               1.03 |
| moss                        |       106029 |               4.4  |               0.23 |               4.3  |               0.23 |               1.66 |
| mt5_large                   |       250100 |               3.89 |               0.26 |               3.79 |               0.26 |               1.47 |
| olmo_7b                     |        50280 |               2.01 |               0.5  |               1.96 |               0.51 |               0.76 |
| orion_14b_chat              |        84608 |               4.63 |               0.22 |               4.52 |               0.22 |               1.75 |
| phi_1                       |        50257 |               1.31 |               0.77 |               1.28 |               0.78 |               0.49 |
| phi_2                       |        50257 |               1.31 |               0.77 |               1.28 |               0.78 |               0.49 |
| pko_t5_large                |        50258 |               0.97 |               1.03 |               0.95 |               1.06 |               0.37 |
| prompt_clue                 |        32128 |               4.34 |               0.23 |               4.24 |               0.24 |               1.64 |
| qwen1_5_14b_chat            |       151643 |               4.16 |               0.24 |               4.06 |               0.25 |               1.57 |
| qwen_1_8b_chat              |       151851 |               4.16 |               0.24 |               4.06 |               0.25 |               1.57 |
| qwen_72b_chat               |       151851 |               4.16 |               0.24 |               4.06 |               0.25 |               1.57 |
| qwen_7b_chat                |       151851 |               4.16 |               0.24 |               4.06 |               0.25 |               1.57 |
| roberta_chinese_clue        |         8021 |               2.7  |               0.37 |               2.64 |               0.38 |               1.02 |
| skywork_13b_base            |        65519 |               3.69 |               0.27 |               3.61 |               0.28 |               1.4  |
| skywork_13b_math            |        65519 |               3.69 |               0.27 |               3.61 |               0.28 |               1.4  |
| solar_10_7b                 |        32000 |               2.36 |               0.42 |               2.3  |               0.43 |               0.89 |
| starchat_alpha              |        49152 |               2.78 |               0.36 |               2.72 |               0.37 |               1.05 |
| switch_c_2048               |        32100 |              14.13 |               0.07 |              13.8  |               0.07 |               5.34 |
| t5_base                     |        32100 |              14.13 |               0.07 |              13.8  |               0.07 |               5.34 |
| t5_large                    |        32100 |              14.13 |               0.07 |              13.8  |               0.07 |               5.34 |
| t5_small                    |        32100 |              14.13 |               0.07 |              13.8  |               0.07 |               5.34 |
| text_davinci_003            |        50281 |               1.31 |               0.77 |               1.28 |               0.78 |               0.49 |
| tigerbot_13b_chat_v2        |        60512 |               4.25 |               0.24 |               4.15 |               0.24 |               1.61 |
| tigerbot_70b_chat_v4_4k     |        65107 |               4.25 |               0.24 |               4.15 |               0.24 |               1.61 |
| wizardcoder_15b_v1          |        49152 |               2.78 |               0.36 |               2.72 |               0.37 |               1.05 |
| wizardcoder_python_7b_v1    |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| wizardlm_7b_v1              |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| wizardmath_70b_v1           |        32000 |               1.84 |               0.54 |               1.8  |               0.56 |               0.7  |
| xlm_roberta                 |       250002 |               3.96 |               0.25 |               3.86 |               0.26 |               1.5  |
| yi_34b                      |        64000 |               4.17 |               0.24 |               4.07 |               0.25 |               1.58 |
| yi_6b                       |        64000 |               4.17 |               0.24 |               4.07 |               0.25 |               1.58 |
| yi_vl34b                    |        64000 |               4.11 |               0.24 |               4.02 |               0.25 |               1.56 |
| zephyr_7b_beta              |        32000 |               2.36 |               0.42 |               2.3  |               0.43 |               0.89 |

</details>




## Reference

- Getting the most out of your tokenizer for pre-training and domain adaptation
- Efficient and Effective Text Encoding for Chinese LLaMA and Alpaca
- https://huggingface.co/spaces/Xenova/the-tokenizer-playground
