# Evaluating Concurrent Robustness of Language Models Across Diverse Challenge Sets

This repository contains the code, datasets, and methods for the paper **"Evaluating Concurrent Robustness of Language Models Across Diverse Challenge Sets"** presented at EMNLP 2024.

## Abstract

Language models (LMs) often demonstrate sensitivity to minor input perturbations, which can hinder their reliability in practical applications. This research introduces a framework to evaluate and improve the robustness of language models across various types of input perturbations. Our approach employs fine-tuning and chain-of-thought (CoT) prompting with exemplars to assess performance across multiple perturbations in models ranging from pre-trained models (PLMs) to large language models (LLMs). The study primarily focuses on the Tabular-NLI task, utilizing the INFOTABS dataset and a variety of perturbation types to test the models' performance under realistic input variations.

## Key Contributions

1. **Multi-Set Inoculation**: A framework to evaluate and fine-tune LMs for robustness against diverse input perturbations. We propose three fine-tuning strategies (Sequential, Mixed-Training, and Dynamic Mix-Training) to address robustness against multiple perturbations concurrently.
   
2. **Adaptation to Large Language Models (LLMs)**: Extending the framework for LLMs, we utilize a few-shot CoT prompting approach with exemplars to avoid the computational costs of fine-tuning while maintaining robustness.

3. **Evaluation on Tabular-NLI Task**: Using the INFOTABS dataset, we test robustness across several types of perturbations, including character, negation, numeric, location, and paraphrasing changes.

## Methodology

### 1. Multi-Set Inoculation Framework
   - **Sequential Fine-Tuning (SEQ)**: Fine-tuning the model on different perturbation sets in sequence.
   - **Mixed-Training (MIX)**: Training on a composite dataset with samples from all perturbation types, ensuring robustness across the board.
   - **Dynamic Mix-Training (DYNMIX)**: Similar to MIX but dynamically allocates samples based on the initial performance of the model on different perturbations.

### 2. LLM Prompting Techniques
   - **Few-shot CoT Prompting**: LLMs are trained with CoT prompting to improve inference stability across perturbations.
   - **Single Exemplars Multiple Prompts (SEMP)** and **Multiple Exemplars Single Prompt (MESP)** approaches: These techniques are designed to introduce LLMs to various perturbations in a single or multiple prompt setting.

## Experimental Setup

- **Datasets**: We utilize the INFOTABS dataset along with its perturbed challenge sets created using NLP tools like TextAttack and manual adjustments. Each perturbation set includes up to 1,500 samples.
- **Models**: Evaluated models include BERT-based PLMs and various LLMs such as GPT-3.5, LLaMA, and Flan-T5.
- **Evaluation Metric**: Model accuracy on perturbed datasets serves as the primary evaluation metric.

## Results and Analysis

Our experiments demonstrate:
- Significant improvement in robustness when models are fine-tuned using mixed and dynamic training strategies.
- Increased stability in LLMs under CoT prompting with exemplars, especially when exposed to diverse input perturbations.

## Citation

If you find this work helpful, please cite our paper:

```bibtex
@inproceedings{gupta-etal-2024-evaluating-concurrent,
    title = "Evaluating Concurrent Robustness of Language Models Across Diverse Challenge Sets",
    author = "Gupta, Vatsal  and
      Pandya, Pranshu  and
      Kataria, Tushar  and
      Gupta, Vivek  and
      Roth, Dan",
    editor = "Al-Onaizan, Yaser  and
      Bansal, Mohit  and
      Chen, Yun-Nung",
    booktitle = "Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing",
    month = nov,
    year = "2024",
    address = "Miami, Florida, USA",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.emnlp-main.1237",
    pages = "22162--22184",
    abstract = "Language models, characterized by their black-box nature, often hallucinate and display sensitivity to input perturbations, causing concerns about trust. To enhance trust, it is imperative to gain a comprehensive understanding of the model{'}s failure modes and develop effective strategies to improve their performance. In this study, we introduce a methodology designed to examine how input perturbations affect language models across various scales, including pre-trained models and large language models (LLMs). Utilizing fine-tuning, we enhance the model{'}s robustness to input perturbations. Additionally, we investigate whether exposure to one perturbation enhances or diminishes the model{'}s performance with respect to other perturbations. To address robustness against multiple perturbations, we present three distinct fine-tuning strategies. Furthermore, we broaden the scope of our methodology to encompass large language models (LLMs) by leveraging a chain of thought (CoT) prompting approach augmented with exemplars. We employ the Tabular-NLI task to showcase how our proposed strategies adeptly train a robust model, enabling it to address diverse perturbations while maintaining accuracy on the original dataset.",
}
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

For additional details, please refer to the paper or contact the authors at `{g.vatsal, p.pandya}@iitg.ac.in`.
