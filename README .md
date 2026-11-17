# RBI Policy Tone Analyzer (NLP with FinBERT)

A Python tool that reads central bank documents (PDF), scores every sentence as positive, negative or neutral with **FinBERT** (an AI model trained on financial text), and compares the tone of two documents.

## Why this project
Markets and analysts read the *tone* of RBI statements, not just the numbers. This project turns text into measurable data.

## How it works
1. Read the PDF(s) with pypdf and split the text into sentences
2. Load the pretrained FinBERT model (ProsusAI/finbert) from Hugging Face
3. Score each sentence: positive, negative or neutral, plus a tone score = P(positive) - P(negative)
4. Summarise with Pandas, plot with Matplotlib, and list the most positive and negative sentences
5. Compare two documents (e.g. RBI MPC statements of August and October 2026)

## Tech stack
Python, Hugging Face Transformers, PyTorch, Pandas, Matplotlib, pypdf, Google Colab

## How to run
Open `RBI_Policy_Tone_Analyzer_FinBERT.ipynb` in Google Colab, run each step in order, and upload one or two PDFs when asked.

## Key findings
*(Write 2-3 findings in your own words after running it, e.g. which statement was more negative and why.)*

## Limitations
- FinBERT is trained on financial news, so "negative" means negative sentiment, not "hawkish" or "dovish"
- Sentences are scored without surrounding context
- Only the first 250 sentences per PDF are scored

## Future improvements
Track tone across many MPC statements over time, add a hawkish/dovish keyword score, and build a Gradio dashboard.
