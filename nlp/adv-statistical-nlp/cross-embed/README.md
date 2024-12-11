# Cross-Lingual Word Embedding Matching for Yoruba-English README

[Repo](https://github.com/smbirnbaum/work/tree/f95255d2495667c5411812b4a3a0bda1d0515331/nlp/adv-statistical-nlp/cross-embed)

A project that compares the performance of `FastText` and `mBert` for word embedding with Yoruba and English as the target languages using cosine similarity.

## Goals:
- Benchmark FastText as a static embedding model.
- Compare FastText's performance with mBERT, a state-of-the-art contextual embedding model.
- Analyze embeddings to identify challenges in low-resource NLP tasks.

---

## Dataset
The dataset consists of paired Yoruba and English sentences extracted from `train.csv`.

### Preprocessing:
- Stripped `ID` column.
- Saved Yoruba and English sentences in separate CSVs (`yoruba_sentences.csv` and `english_sentences.csv`).
- Limited the dataset to subsets of 50, 250, or the full dataset (16,870 sentences) for different experiments.

---

## Workflow
The pipeline includes:

1. **Data Preprocessing:**
   - Extract Yoruba and English sentences from the dataset.
   - Split sentences into separate `.csv` files for evaluation.

2. **Embedding Evaluation:**
   - Use FastText and mBERT to calculate cosine similarity between sentence pairs.
   - Save results in `yoruba_english_sentence_comparison.csv`.

3. **Statistical Analysis:**
   - Compare FastText and mBERT performance using t-tests.
   - Measure robustness by running on multiple random subsets of sentences.

4. **Error Analysis:**
   - Examine repetitive matches and mismatched pairs.
   - Visualize embedding clusters using PCA.

---

## Results
### Key Findings:
- **FastText:**
  - Struggles with sentence-level understanding, resulting in low similarity scores (e.g., 0.05–0.14).
- **mBERT:**
  - Demonstrates better contextual understanding, with higher similarity scores (e.g., 0.45–0.61).
- **PCA Visualization:**
  - Yoruba and English embeddings are well-separated in mBERT's embedding space.

---

## Files

### Input Files:
- `train.csv`: Original dataset containing paired Yoruba and English sentences.
- `yoruba_sentences.csv`: Processed Yoruba sentences.
- `english_sentences.csv`: Processed English sentences.

### Output Files:
- `yoruba_english_sentence_comparison.csv`: Sentence-level comparison of FastText and mBERT results.

### Dependencies:
Dependencies are listed in `requirements.txt`, generated using:
```bash
pip freeze > requirements.txt
```

Install dependencies with:
```bash
pip install -r requirements.txt
```

### Running the Script:

If you don't want to use Jupyter notebook:

```bash
python yoruba_project.py
```


## Limitations & Future Work

### Limitations:
- Repetitive matches observed in mBERT due to dataset size.
- FastText embeddings are limited in sentence-level contextual understanding.

### Future Improvements:
- Expand dataset for more diverse examples.
- Fine-tune mBERT on Yoruba-English translation data.
- Explore advanced multilingual models like XLM-R.

## Credits
- Developed by Shawna Birnbaum.
- Part of the **LING 582 Fall 2024 Course Project** at the University of Arizona.