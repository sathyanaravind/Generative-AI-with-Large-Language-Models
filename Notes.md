## Generative AI with LLMs

### Generative AI use cases, project lifecycle, and model pre-training

- [Prompt and completions](#prompt-and-completions)  
- [Transformers](#Transformers)  
- [Prompting and prompt engineering](#prompting-and-prompt-engineering)  
- [Generative configuration inference parameters](#Generative-configuration-inference-parameters)  
- [Generative AI Project Life Cycle](#Generative-AI-Project-Life-Cycle)  
- [Pre-training and Scaling laws](#Pre-training-and-Scaling-laws)
- [Model architecture and pre-training objective](#Model-architecture-and-pre-training-objective)
- [Computational Challenges](#Computational-Challenges)
- [Compute budget]
    - [Quantization](#Qutanization)
    - [Efficient Multi-GPU Compute Strategies](#Efficient-Multi-GPU-Compute-Strategies)
    - [Chinchilla](#Chinchilla)
    - 
### Fine-tuning and evaluating large language models

### Reinforcement learning and LLM-powered applications


Generative AI is a general-purpose technology like electricity.

- foundation models also called Base models. Eg: BERT, GPT, FLAN-T5, LLaMa, BLOOM, PaLM
- parameters - also called memory. Models with more parameters can capture more understanding of the language
- 
### Prompt and completions
- prompt: text passed into the llm
- context window: space or memory available for the prompt
- completion: output of a model. Typically 1000 words but differs for different models
<img width="862" alt="image" src="https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/7d6157a9-2894-44ba-a26c-beb964526249">

- LLM use cases and tasks: essay writing, summarising, translating, code generation, entity


### Transformers
- scale efficiently, parallel process, attention to input meaning
- df
-   the power of the transformer is to learn the relevance of all the words in the sentence to every other and to apply attention weights to these relations
-   attention weights are learned during the llm training
-   Transformer working
    - Encoder: input tokenizer -> embedding -> positional encoding -> multi-headed self-attention -> feed-forward network -> softmax layer
    - Decoder: 
    - self-attention - the importance of each word to all other words in the input
- models
  - encoder models: BERT
  - encode decoder models: BART, T5
  - decoder models: GPT, BLOOM, LLaMa

### Prompting and prompt engineering
- In-context learning(ICL): providing examples of tasks inside the context window
  - zero shot inference: provide no example. Large llms are good at this and not small
  - one shot inference: inclusion of one example in the prompt
  - few shot inference: a few examples
- generally, if the model underperforms even with 5-6 examples consider fine-tuning

### Generative configuration - inference parameters
- **max new tokens**: no of tokens the model will generate
- greedy vs random sampling
    - greedy: word with the highest probability is selected from the softmax output. Prone to repetition
    - random: select a token using random-weighted sampling across the softmax outputs. For more creativity
- **sample top K**: select the number of tokens to choose from randomly
- **sample top P**: specify the total probability to choose from
- **temperature**: it is a scaling factor that applies to the final softmax output and controls the shape of the probability distribution the model calculates for the next word. The higher the temperature higher the randomness. In contrast to top K and top P change in temperature value can alter the predictions of the model.

### Generative AI Project Life Cycle

![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/f2dea306-5e58-4999-a1e5-e6d64af99b64)

#### Pre-training and Scaling laws
After deciding the scope of the LLM application the next step is to choose the the model. Here we can either use a 
1. Foudational model: pre-trained LLM or
2. Train our own model: custom LLm  
   In general, always a foundational model is used. There are many open-source and private model hubs available like the huggingface model hub. These hubs also contain model cards which include information about the models such as
- model details,
- uses, bias, risk and limitations,
- training details 
- evaluation
#### Model architecture and pre-training objectives**
  LLMs encode a deep statistical representation of language during pre-training on a vast amount of unstructured textual data. Pre-training requires a lot of compute and due to bias and bad quality of data often only 1-3 % of tokens are used.
- Autoencoding models: encoder
    - pre-trained using **Masked Language Modeling(MLM)**
    - objective: reconstruct text("denoising")
    - bidirectional context: knows the full context of the token not just previous tokens
    - use cases: sentimental analysis, names entity recognition, word classification
    - eg: BERT, ROBERTA
- Autoregressive models: decoder
    - pre-trained using **Causal Language Modeling(CLM)**
    - objective: predict next token
    - unidirectional context
    - use cases: text generation, other emergent behaviours
    - eg: GPT, BLOOM
- Sequence to Sequence Models:
    - pre-training objective changes from model to model, taking T5 as an example
    - pre-train the encoder with span correction: **mask random input tokens** and replace them with **sentinel token**(random tokens not in vocabulary)
    - objective: reconstruct span
    - use cases: translation, summarization, Q&A
    - T5, BART

![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/9e5d59c5-223b-4512-9ac4-a46776245a2c)

#### Computational Challenges

- approximate GPU RAM for 1B parameters  
1 parameter = 4 bytes(32-bit float)  
1B parameters = 4*10^9 = 4GB  
memory to store model: 4GB @ 32bit full precision  
memory to train model: 24GB @ 32bit full precision  
too much for consumer hardware  
- to fix: quantization, distributed training, finetuning   

![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/ea99112a-d21f-4a17-8e3f-df2797602397)

- Quantization
    - aim is to reduce required memory to store and train models
    - statistically projects the original 32-bit floating point numbers to lower precision spaces using scaling factors
    - Quantization-aware-training(QAT) learns quantization scaling factors during training
    - **BFLOAT16** popular choice
#### Efficient Multi-GPU Compute Strategies
### Scaling laws and compute optimal models

- scaling choice for pre-training
    - goal: maximize performance
    - constraint: compute budget(GPU, training time, cost)
    - scaling choice: increase data size(no of tokens) or model size(no of parameters)
- compute budget
    - 1 petaflop/s-days : # floating point operations performed at 1 petaflop per second for one day
    - ie, 8 V100 or 2 A100 GPUs running at full efficiency for 24 hrs
- no of petflops/s-day to pretrain various llms
![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/5ed8289b-c832-4359-a504-ff9bd74d2a41)

- from the paper "Scaling laws for Neural Language Models" the test loss decreases with dataset size, compute budget and performance if the other two are kept constant and follow the power law
![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/293d0567-36d3-41a3-9c25-a2bc8a857348)
- Chinchilla scaling laws for model and dataset size
    - very large models may be over-parametrized and under-trained
    - smaller models trained on more data could outperform large models
    - compute optimal training datasize is ~20x the no of parameters

![image](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/80b0da9a-29e8-4850-9d71-7bc32c11f95d)

#### Pre-training for domain adaptation



