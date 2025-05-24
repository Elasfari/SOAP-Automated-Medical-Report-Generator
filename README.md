# SOAP Automated Medical Report Generator

## Overview

This project focuses on automating the generation of SOAP (Subjective, Objective, Assessment, Plan) notes using fine-tuned large language models (LLMs). The study evaluates five models—Small T5, Facebook BART Large, LLaMA 3 2.3B, Tiny LLaMA, and Microsoft Phi-2—using various fine-tuning techniques. A judge model powered by Grok's LLaMA 3 70B assesses the quality of generated SOAP notes based on completeness, correctness, organization, and clinical relevance. The project achieves its best performance with LLaMA 3 2.3B using prefix tuning, scoring 7.9475 on the judge model.

## Directory Structure

The project directory (`SOAP-Automated-Medical-Report-Generator/Code`) contains the following Jupyter Notebook files:

- **Adapters.ipynb** (625 KB): Implements adapter learning for fine-tuning Tiny LLaMA.
- **Full_Parameter.ipynb** (243 KB): Implements full-parameter tuning for fine-tuning Small T5.
- **judge-model.ipynb** (14 KB): Contains the evaluation logic using Grok's LLaMA 3 70B as the judge model.
- **Prefix.ipynb** (162 KB): Implements prefix tuning for fine-tuning LLaMA 3 2.3B.
- **Transfer_Learning.ipynb** (74 KB): Implements transfer learning for fine-tuning Facebook BART Large.

## Dataset

The project uses the `om1-health/medical-dialogue-to-soap-summary` dataset from Hugging Face, which includes 10,000 synthetic medical conversations paired with SOAP note summaries. The dataset is split into:

- Training: 9,250 samples
- Validation: 500 samples
- Testing: 250 samples

## Requirements

To run the notebooks, ensure you have the following dependencies installed:

- Python 3.8+
- Jupyter Notebook
- Libraries: `transformers`, `datasets`, `torch`, `evaluate`, `rouge_score`, `bert_score`

You can install the required libraries using:

```bash
pip install transformers datasets torch evaluate rouge_score bert_score
```

## Running the Code

1. Clone the repository or navigate to the project directory:

   ```bash
   cd Desktop/NLP/Project/SOAP-Automated-Medical-Report-Generator/Code
   ```
2. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```
3. Open and run the desired notebook (e.g., `Prefix.ipynb` for prefix tuning with LLaMA 3 2.3B).
4. The `judge-model.ipynb` notebook can be run separately to evaluate the generated SOAP notes.

## Results

The models were evaluated using lexical, semantic, and quality-based metrics:

- **LLaMA 3 2.3B (Prefix Tuning)** achieved the highest judge model score of 7.9475.
- **Facebook BART Large (Transfer Learning)** scored 6.1 on the judge model.
- Other models like Tiny LLaMA and Microsoft Phi-2 had lower scores due to their compact sizes.

For detailed results, refer to the paper (`Paper.pdf`) in the project directory.

## Authors

- Yassin Saad
- Michael Adel
- Michael Wagdy
- Sara Aboalyazeed
- Ziad Maher

Department of Artificial Intelligence, Nile University, Egypt

## License

This project is licensed under the MIT License.