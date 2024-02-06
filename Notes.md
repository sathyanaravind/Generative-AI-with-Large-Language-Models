## Generative AI with LLMs

-[Prompt and completions](#prompt-and-completions)  
-[Transfomers](####Transfomers)  
-[Prompting and prompt engineering](#prompting-and-prompt-engineering)  
-[Generative configuration - inference parameters](####Generative-configuration-inference-parameters)  
-[Generative AI Project Life Cycle](####Generative-AI-Project-Life-Cycle)  


Generative AI is a general-purpose technology like electricity.

- foundation models also called Base models. Eg: BERT, GPT, FLAN-T5, LLaMa, BLOOM, PaLM
- parameters - also called memory. Models with more parameters can capture more understanding of the language
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
    - Encoder: input tokenizer -> embedding -> positional encoding -> multi-headed self-attention -> feed-forward network -> softmax layer
    - Decoder: 
    - self-attention - the importance of each word to all other words in the input
- models
  - encoder models: BERT
  - encode decoder models: BART, T5
  - decoder models: GPT, BLOOM, LLaMa

#### Prompting and prompt engineering
- In-context learning(ICL): providing examples of tasks inside the context window
  - zero shot inference: provide no example. Large llms are good at this and not small
  - one shot inference: inclusion of one example in the prompt
  - few shot inference: a few examples
- generally, if the model underperforms even with 5-6 examples consider fine-tuning

#### Generative configuration - inference parameters
- **max new tokens**: no of tokens the model will generate
- greedy vs random sampling
    - greedy: word with the highest probability is selected from the softmax output. Prone to repetition
    - random: select a token using random-weighted sampling across the softmax outputs. For more creativity
- **sample top K**: select the number of tokens to choose from randomly
- **sample top P**: specify the total probability to choose from
- **temperature**: it is a scaling factor that applies to the final softmax output and controls the shape of the probability distribution the model calculates for the next word. The higher the temperature higher the randomness. In contrast to top K and top P change in temperature value can alter the predictions of the model.

#### Generative AI Project Life Cycle

