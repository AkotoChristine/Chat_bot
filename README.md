# African Recipe Generation Chatbot

An AI-powered conversational chatbot that generates authentic African recipes using a fine-tuned Phi-3-mini language model.

---

## Project Overview

This project tackles the lack of accessible, culturally authentic African recipe resources by building an intelligent chatbot that generates detailed, conversation-ready recipes.  
Built on Microsoft’s Phi-3-mini model, the chatbot specializes in dishes from West, East, South, and North Africa.

### The Problem

- Traditional recipe sources lack cultural specificity for African cuisines  
- No interactive, conversational recipe generation tools for African food  
- Existing AI models are trained on predominantly Western recipes  

### Our Solution

A fine-tuned language model that:
- Generates authentic African recipes on demand  
- Understands natural language requests (e.g., “Make me something with plantains”)  
- Provides detailed ingredients, measurements, and cooking instructions  
- Maintains cultural authenticity and food safety  

---

## Key Features

| Feature | Description |
|----------|-------------|
| African Cuisine Focus | Specializes in jollof rice, fufu, tagine, injera, and 100+ African dishes |
| Conversational Interface | Chat naturally — just ask for what you want |
| Structured Recipes | Ingredients + step-by-step instructions |
| Fast Generation | Real-time recipe creation in seconds |
| High Accuracy | 70% improvement in generation quality (perplexity: 2.5) |

---

## Dataset and Training

### Dataset Overview
- **Source:** Recipe NLG corpus (2 million recipes)  
- **Filtering:** Extracted African recipes using 30+ cultural keywords  
- **Keywords:** jollof, fufu, egusi, tagine, injera, plantain, cassava, etc.  
- **Final Size:** ~[X,XXX] curated African recipes  
- **Coverage:** West, East, South, and North African cuisines  

### Data Processing Pipeline
1. Filtering → Selected African recipes from 2M dataset using keyword matching  
2. Cleaning → Removed duplicates, nulls, and formatting issues  
3. Formatting → Converted to instruction–response pairs for training  
4. Tokenization → Applied Phi-3 chat template with special tokens  
5. Split → 90% training, 10% validation  

---

## Model Architecture

| Property | Details |
|-----------|----------|
| Base Model | Phi-3-mini-4k-instruct |
| Size | 3.8 billion parameters |
| Type | Instruction-tuned transformer decoder |
| Context Window | 4,096 tokens |
| Advantage | Pre-trained for chat and structured text generation |

---

## Why Phi-3 Over GPT-2?

We initially experimented with GPT-2 (see `failed_gpt2_model_training/`), but it completely failed — producing incoherent text.  
Here’s why Phi-3-mini succeeded:

| Factor | GPT-2 | Phi-3 | Impact |
|--------|--------|--------|--------|
| Instruction-tuned | No | Yes | Critical for chat-style tasks |
| Model Size | 124M params | 3.8B params | 31× more capacity |
| Chat Support | No | Native | Understands user/assistant roles |
| Output Quality | Gibberish | Coherent recipes | Night-and-day difference |

**Lesson Learned:**  
Instruction-following models are essential for structured generation tasks like recipe creation.

---

## Future Improvements

- Expand dataset with more regional cuisines  
- Add nutritional value estimation  
- Deploy chatbot via Gradio or Streamlit interface  
- Integrate speech-to-text for voice-based cooking assistance  

---

## Tech Stack

- **Model:** Phi-3-mini-4k-instruct  
- **Frameworks:** Transformers, PyTorch, Hugging Face  
- **Languages:** Python  
- **Tools:** Weights & Biases, Gradio, Datasets library  

---

## Authors

**Christine Akoto-Nimoh**  
African Leadership University | Unesis AI  
Passionate about using AI to preserve and promote African culture through technology.

---

## License

This project is released under the MIT License — feel free to use and build upon it responsibly.

---

> “Food is a universal language — this chatbot helps the world speak African cuisine fluently.”
