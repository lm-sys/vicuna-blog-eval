This repo is an archive of the code and data used in the [vicuna blog post](https://lmsys.org/blog/2023-03-30-vicuna/).

**This repo is deprecated and we recommend using our new question set and evaluation pipeline at [fastchat.llm_judge](https://github.com/lm-sys/FastChat/tree/main/fastchat/llm_judge).**

We do not recommend using this repo because its questions are relatively easy and it does not address limitations of GPT-4 based evaluation such as [position bias](https://arxiv.org/abs/2306.05685).

---------------

## Evaluation

Our AI-enhanced evaluation pipeline is based on GPT-4. This section provides a high-level summary of the pipeline. For detailed instructions, please refer to the [evaluation](eval) documentation.

### Pipeline Steps

1. Generate answers from different models: Use `qa_baseline_gpt35.py` for ChatGPT, or specify the model checkpoint and run `get_model_answer.py` for Vicuna and other models.

2. Generate reviews with GPT-4: Use GPT-4 to generate reviews automatically. This step can also be performed manually if the GPT-4 API is not available to you.

3. Generate visualization data: Run `generate_webpage_data_from_table.py` to generate data for a static website, which allows you to visualize the evaluation data.

4. Visualize the data: Serve a static website under the `webpage` directory. You can use `python3 -m http.server` to serve the website locally.

### Data Format and Contribution

We use a data format encoded with JSON Lines for evaluation. The format includes information on models, prompts, reviewers, questions, answers, and reviews.

You can customize the evaluation process or contribute to our project by accessing the relevant [data](eval/table/).

For detailed instructions, please refer to the [evaluation](eval) documentation.
