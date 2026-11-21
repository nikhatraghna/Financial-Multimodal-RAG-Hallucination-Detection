
# Financial Multimodal RAG Hallucination Detection

A research project investigating how hallucination detectors transfer from textual to visual evidence in financial question answering, and whether structured numerical verification improves answer reliability.

## Research Overview

This project evaluates hallucination detection and mitigation in financial Multimodal Retrieval-Augmented Generation (RAG). It compares text, document images, OCR-extracted text, and combined visual-textual evidence.

## Methodology

- **Model:** Qwen3-VL-2B-Instruct
- **Retrieval:** BM25 + BGE-small-en-v1.5 with Reciprocal Rank Fusion
- **Evidence Conditions:**
  - E1: PDF Text
  - E2: Page Images
  - E3: OCR Text
  - E4: Images + OCR Text
- **Baselines:** Unverified generation, NLI-based detection, context-sensitivity methods, REFIND-inspired detection, and basic numerical verification.
- **Proposed Method:** Structured evidence-conditioned verification using numerical, unit, reporting-period, and entity consistency checks, followed by correction or abstention.

## Datasets

- **FinRAGBench-V:** 169 matched test questions and 210 retrieval-evaluation questions.
- **FinChart-Bench:** 200 additional financial chart questions.

## Running the Project

1. Open `Financial_CrossModal_Hallucination_Research_3.ipynb` in Google Colab.
2. Select **Runtime → Change runtime type → GPU**.
3. Execute the notebook cells in order.
4. Review the generated evaluation results, tables, and visualizations.

## Evaluation

The project evaluates:

- Numerical answer accuracy
- Hallucination detection (Precision, Recall, F1)
- Hallucination rates
- Correction and abstention rates
- Cross-modal transfer performance
- Statistical comparisons and sensitivity analysis

## Key Findings

Structured verification reduced reported hallucination rates in several settings, but often increased abstention and reduced overall answer accuracy. The evaluation uses automatically derived silver labels rather than human-verified hallucination annotations.

The REFIND-inspired baseline is a modified reimplementation, and the full-run component ablation remains incomplete.

## Research Report

The IEEE-format research report includes the literature review, methodology, baseline comparisons, experimental findings, statistical analysis, and limitations.


MS Data Science  
FAST National University of Computer and Emerging Sciences (FAST-NUCES)
