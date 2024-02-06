## Generative AI with LLMs

Generative AI is a general-purpose technology like electricity.

- foundation models also called Base models. Eg: BERT, GPT, FLAN-T5, LLaMa, BLOOM, PaLM
- parameters - also called memory. Models with more paramemters are able to capture more understanding of the language
- 
#### Prompt and completions
- prompt: text passed into the llm
- context window: space or memory available for the prompt
- completion: output of a model. Typically 1000 words but differs for different models
<img width="862" alt="image" src="https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/assets/77285092/7d6157a9-2894-44ba-a26c-beb964526249">

- LLM use cases and tasks: essay writing, summarising, translating, code generation, entity


#### Transformers
- scale efficiently, parallel process, attention to input meaning
- df
-   the power of the transformer is to learn the relevance of all the words in the sentence to every other and to apply attention weights to these relations
-   attention weights are learned during the llm training
-   Transformer working
Encoder: input tokenizer -> embedding -> positional encoding -> multi-headed self-attention -> feed-forward network -> softmax layer
Decoder: 
    - self-attention - the importance of each word to all other words in the input
  - encoder models: BERT
  - encode decoder models: BART, T5
  - decoder models: GPT, BLOOM, LLaMa

#### Prompting and prompt engineering
- In-context learning(ICL): providing examples of tasks inside the context window
  - zero shot inference: provide no example. Large llms are good at this and not small
  - one shot inference: inclusion of one example in the prompt
  - few shot inference: a few examples
- generally, if the model underperforms even with 5-6 examples consider fine-tuning

