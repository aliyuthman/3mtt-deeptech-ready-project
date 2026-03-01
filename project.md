Assessment Title: Building a Production-Ready Abstractive Summarizer 

Primary Tool: Hugging Face Transformers (T5 Model) 

Shape 

Scenario 

You have just been hired as an NLP Engineer at a digital media startup called QuickNews. The company ingests thousands of long-form articles daily. Your Product Manager wants a feature that automatically generates concise, 2-sentence summaries for the mobile app notification feed. 

Your task is to build a Text-to-Text generation pipeline using the T5 (Text-to-Text Transfer Transformer) model. You must handle data formatting, generation strategies, and performance evaluation. 

Shape 

Task 1: The "Text-to-Text" Data Pipeline 

Objective: Master the input formatting specific to T5 architecture. 

Unlike BERT, T5 treats every task as a text generation problem. It requires a specific "trigger phrase" or prefix to understand the task intent. 

Load Data: Find one long article (at least 3 paragraphs) about a current topic from a Nigerian source (e.g., Punch, Vanguard, or TechCabal). Examples include "The expansion of Starlink in Nigeria" or "Updates on the Naira exchange rate." Store this text in a Python variable called news_article. 

Preprocessing Function: Write a Python function preprocess_for_t5(text) that: 

Cleans the text (removes double spaces, strips whitespace). 

Crucial Step: Prepends the prefix "summarize: " to every input string. 

Tokenization: Tokenize the output of your function using T5Tokenizer. Ensure you handle padding and truncation (max length = 512). 

Deliverable: 

A code snippet showing the "Before" (raw text) and "After" (tokenized input with prefix) for the example article. 

Shape 

Task 2: Decoding Strategies (Inference) 

Objective: Understand how decoding algorithms affect the quality of generated text. 

You need to generate summaries for the article you selected in Task 1. You must implement two different decoding strategies to demonstrate the trade-off between speed and quality. 

Strategy A (Greedy Search): Run the model with num_beams=1. 

Strategy B (Beam Search): Run the model with num_beams=5 and no_repeat_ngram_size=2 (to prevent the model from repeating itself). 

Deliverable: 

Print the generated summary for Strategy A. 

Print the generated summary for Strategy B. 

Brief Analysis (50 words): Which summary was more coherent? Did Strategy A suffer from repetition? 

Shape 

Task 3: Quantitative Evaluation (ROUGE Metrics) 

Objective: Evaluate model performance using standard industry metrics. 

Subjective reading is not enough for deployment. You must quantify how much your generated summary overlaps with a human-written "Gold Standard." 

Create a Reference: Since you selected your own article, read it and write your own "perfect" 1-sentence summary. This will serve as your Gold Standard (Reference). 

Calculate ROUGE: Use the rouge-score or evaluate library. 

Compare: Calculate the ROUGE-1 (unigram overlap) and ROUGE-L (structure overlap) scores between your Strategy B summary and the Reference summary you wrote in step 1. 

Deliverable: 

A Python script that outputs the final ROUGE scores. 

Shape

