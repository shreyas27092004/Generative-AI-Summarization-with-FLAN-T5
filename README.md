# Generative AI Summarization with FLAN-T5

This repository contains a lab from the Coursera course "Generative AI with Large Language Models". The project demonstrates how to use a pre-trained Large Language Model (LLM) for dialogue summarization and explores various prompt engineering techniques to improve the quality of the generated summaries.

## Overview

The core task is to take a conversation and generate a concise summary. This lab uses the `google/flan-t5-base` model and the `knkarthick/dialogsum` dataset from Hugging Face.

The notebook walks through a progression of prompting techniques, starting with a basic prompt and moving to more advanced methods, to show how they impact the model's performance.

## Key Concepts Explored

* **Zero-Shot Inference**: The model is given an instruction to summarize the dialogue without any prior examples. The lab shows how a simple instruction can guide the model to perform the correct task.
* **One-Shot Inference**: To improve results, the model is provided with a single, complete example of a dialogue and its corresponding summary. This "in-context learning" helps the model better understand the expected output format and style.
* **Few-Shot Inference**: This technique extends one-shot inference by providing multiple dialogue-summary pairs in the prompt. This gives the model more context and generally leads to more nuanced and accurate summaries.
* **Prompt Templates**: The lab uses specific prompt structures, including one from the official FLAN-T5 templates, to format the input for better results.
* **Generative Configuration**: The lab demonstrates how to adjust inference parameters using the `GenerationConfig` class, such as `max_new_tokens`, `do_sample`, and `temperature`, to control the length and creativity of the generated text.

## How to Run the Lab

1.  **Clone the repository:**
    ```bash
    git clone <https://github.com/shreyas27092004/Generative-AI-Summarization-with-FLAN-T5>
    cd Generative-AI-Summarization-with-FLAN-T5
    ```

2.  **Install Dependencies:**
    The notebook installs all required libraries. The primary packages include `transformers`, `datasets`, `torch`, and `evaluate`.

3.  **Run the Notebook:**
    Open `Lab_1_summarize_dialogue.ipynb` in a Jupyter environment and execute the cells sequentially to see the process from setup to few-shot inference.

## Observations and Results

* **Without Prompt Engineering**: The base FLAN-T5 model, when given only the dialogue, fails to understand the summarization task and instead attempts to continue the conversation.
* **With Instruction Prompts (Zero-Shot)**: Adding a simple instruction like "Summarize the following conversation." significantly improves the output, making the model perform the correct task, although the summaries can be basic.
* **With In-Context Learning (One-Shot & Few-Shot)**: Providing one or more examples drastically improves the quality of the summaries. The model learns the desired tone and structure from the examples, producing outputs that are much closer to the human-written baseline summaries.
* **Limitations**: The lab notes that few-shot inference doesn't always offer a massive improvement over one-shot and that performance is constrained by the model's maximum context length (512 tokens for FLAN-T5-base).
