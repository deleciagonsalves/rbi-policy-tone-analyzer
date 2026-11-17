# RBI Policy Tone Analyzer (NLP with FinBERT)

A Python tool that reads central bank documents (PDF), scores every sentence as positive, negative or neutral with FinBERT (an AI model trained on financial text), and shows the overall tone.

## Why this project
Markets and analysts read the tone of RBI statements, not just the numbers. This project turns text into measurable data.

## How it works
1. Read the PDF with pypdf and split the text into sentences
2. Load the pretrained FinBERT model (ProsusAI/finbert) from Hugging Face
3. Score each sentence: positive, negative or neutral, plus a tone score = P(positive) - P(negative)
4. Summarise with Pandas, plot with Matplotlib, and list the most positive and negative sentences

## Tech stack
Python, Hugging Face Transformers, PyTorch, Pandas, Matplotlib, pypdf, Google Colab

## How to run
Open the notebook in Google Colab, run each step in order, and upload one or two PDFs when asked.

## Data used
A Brickwork Ratings note on the RBI's October 2026 Monetary Policy Committee outcome (not the RBI statement itself).

## Key findings
- The most negative sentences were about falling forex reserves, a flatter yield curve and slowing growth.
- The most positive were about a supportive credit backdrop and growth strong enough to absorb a short tightening cycle.
- The model misread some factual sentences. For example, a sentence about rate increases scored positive, and so did one about rising inflation pressure.

## Limitations
- FinBERT is trained on financial news, so "negative" means negative sentiment, not "hawkish" or "dovish"
- Sentences are scored without surrounding context
- Only one document was analysed, so there is no comparison over time yet

## Future improvements
Compare several MPC statements over time, add a hawkish/dovish keyword score, and build a Gradio dashboard.
