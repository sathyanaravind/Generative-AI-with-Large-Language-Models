# Generative-AI-with-Large-Language-Models

Notes for the [Generative AI with Large Language Models (LLMs)](https://www.deeplearning.ai/courses/generative-ai-with-llms/) from DEEPLEARNING.AI

## Course Materials
### [Week 1: Generative AI use cases, project lifecycle, and model pre-training](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/tree/main/Week%201%3A%20Generative%20AI%20use%20cases%2C%20project%20lifecycle%2C%20and%20model%20pre-training)

- Introduction to LLMs and the generative AI project lifecycle
- LLM pre-training and scaling laws


### [Week 2: Fine-tuning and evaluating large language models](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/tree/main/Week%202%3A%20Fine-tuning%20and%20evaluating%20large%20language%20models)

- Fine-tuning LLMs with instruction
- Parameter efficient fine-tuning

### [Week 3: Reinforcement learning and LLM-powered applications](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/tree/main/Week%203%3A%20Reinforcement%20learning%20and%20LLM-powered%20applications)

- Reinforcement learning from human feedback
- LLM-powered applications
- Course conclusion and ongoing research


### Notes

### [Week 1: Generative AI use cases, project lifecycle, and model pre-training](https://github.com/sathyanaravind/Generative-AI-with-Large-Language-Models/tree/main/Week%201%3A%20Generative%20AI%20use%20cases%2C%20project%20lifecycle%2C%20and%20model%20pre-training)
  - Generative AI and LLMs
  - LLM Use Case and Tasks
  - Text Generation Before Transformers
  - Transformers Architecture
  - Generating Text with Transformers
  - Transformers: Attention is All You Need
  - Prompting and Prompt Engineering
  - Generative Configuration
  - Generative AI Project Lifecycle

Introduction to LLMs and the generative AI project lifecycle    

Prompt  
Context window  
Model  
Completion  
Inference  

Use cases and tasks  
LLM chatbots, essay writing, summarization, translation, information retrieval  

RNN  

Transformers  
-  scale efficiency  
- parallel process  
- attention to input meaning  

Transformer architecture  
Encoder and Decoder  
Encoder   
Input - Tokenizer- Embedding-Positional Encoding  
Self-attention  
Multi-headed self-attention  
Feed-forward network  
Decoder  
Multi-headed self-attention  
Feed-forward network  
softmax output  

Different transformers  
Enoder Only Models  
Encoder Models  
Decoder Models  

Prompting and prompt engineering  
In-context learning(ICL) 
Zero shot inference  
One shot inference  
Few shot inference  

the performance of few shot inference saturates at  5 or 6 examples  
significance of scale : task ability  
larger the scale larger the language understanding  

Generative configuration parameters for inference  
Max new tokens  
Sample top k  
Sample top p   
Temperature  
greedy sampling  
random(weighted) sampling  

Generative AI project lifecycle  
Scope
- Define the use case
Select  
-  Choose an existing model or pretrain your own
Adapt and align model  
- Prompt
engineering
- Fine-tuning
- Align with human feedback  
- Evaluate
Application integration   
- Optimize and deploy the model for inference
- Augment model and build LLM-powered applications

Pre-training and scaling laws  

Computational challenges  



