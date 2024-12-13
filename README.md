# Beyond Data Quantity: Key Factors Driving Performance in Multilingual Language Models

This repository contains materials and code for the paper:

**Beyond Data Quantity: Key Factors Driving Performance in Multilingual Language Models**  
*Sina Bagheri Nezhad, Ameeta Agrawal, Rhitabrat Pokharel*  
To be presented at the **First Workshop on Language Models for Low-Resource Languages**  
*The 31st International Conference on Computational Linguistics (COLING 2025), Abu Dhabi, UAE.*

---

## Overview

Multilingual Language Models (MLLMs) have revolutionized natural language processing by enabling cross-lingual understanding and generation. However, significant performance disparities persist across languages, particularly for low-resource languages.

This paper conducts a comprehensive analysis of **12 key features** that drive MLLM performance across 204 languages. By using **regression models** and **SHAP values**, we identify factors beyond data quantity that significantly impact model effectiveness, including:

- **Token Similarity**: Highlights cross-lingual transfer facilitated by shared vocabulary.
- **Country Similarity**: Demonstrates the influence of cultural and linguistic overlap.
- **Model Size** and **Pre-train Data Percentage**: Confirm their central roles in determining performance.

We evaluate three prominent multilingual models (Bloom, BloomZ, XGLM) using:
- **SIB-200**: For topic classification tasks.
- **Flores-200**: For machine translation tasks.

---

## Key Contributions

1. **Comprehensive Feature Analysis**: Investigated 12 model and language-specific features.
2. **Dual Task Evaluation**: Conducted classification (SIB-200) and translation (Flores-200) tasks across zero-shot and two-shot settings.
3. **Feature Importance Using SHAP**: Quantified the impact of features driving performance disparities.
4. **Practical Insights**: Offered guidelines to improve model performance for underrepresented languages.

---

## Datasets

### SIB-200 Dataset
- **Description**: A topic classification benchmark for 204 languages.
- **Instances**: 204 samples per language.
- **Source**: Derived from Flores-200 and optimized for classification tasks.
- **Reference**: [SIB-200 Dataset](https://github.com/dadelani/sib-200).

### Flores-200 Dataset
- **Description**: A multi-way parallel corpus covering 204 languages.
- **Task**: Machine translation (generation) benchmark.
- **Reference**: [Flores-200](https://github.com/facebookresearch/flores/tree/main/flores200).

---

## Features Analyzed

We explored **12 distinct features** influencing MLLM performance:

### Model-Specific Features:
1. **Model Size**: Number of parameters.
2. **Pre-train Data Percentage**: Proportion of pre-training data per language.
3. **Instruction Tuning Data**: Additional fine-tuning data (specific to BloomZ).

### Language-Specific Features:
4. **Geographical Proximity**: Physical closeness between languages.
5. **Country Similarity**: Sociopolitical overlap of languages.
6. **Language Family**: Genetic classification of languages.
7. **Script Type**: Writing system used by languages.
8. **Token Similarity**: Vocabulary overlap across languages.

### Resource and Demographic Features:
9. **Population**: Number of speakers of a language.
10. **Language Vitality**: Risk of endangerment (Ethnologue classification).
11. **Digital Language Support**: Digital presence and tools.
12. **Resource Level**: Availability of linguistic resources.

---

## Methods

1. **Model Evaluation**: Three multilingual models (Bloom, BloomZ, XGLM) tested in:
   - Zero-shot learning.
   - Two-shot learning.
2. **Tasks**:
   - **Classification**: Using the SIB-200 dataset.
   - **Generation**: Using the Flores-200 dataset.
3. **Feature Analysis**:
   - Applied **10 regression models** (XGBoost, Random Forest, Gradient Boosting, etc.).
   - Used **SHAP values** to identify and quantify feature importance.

---

## Results

### Key Findings:
- **Token Similarity** and **Country Similarity** emerged as significant predictors of performance.
- **Model Size** and **Pre-train Data Percentage** confirmed their importance in driving MLLM effectiveness.
- **Geographical Proximity** had moderate impact, while **resource-level features** like Population and Digital Support were less critical.

### Regression Results:
| Task Setup       | Bloom             | BloomZ            | XGLM             |
|------------------|-------------------|-------------------|------------------|
| **Classification** |                   |                   |                  |
| Zero-Shot        | Random Forest (R²=0.645) | Random Forest (R²=0.903) | XGBoost (R²=0.855) |
| Two-Shot         | XGBoost (R²=0.847) | Gradient Boosting (R²=0.754) | XGBoost (R²=0.902) |
| **Generation**     |                   |                   |                  |
| Zero-Shot        | Gradient Boosting (R²=0.553) | Gradient Boosting (R²=0.918) | XGBoost (R²=0.902) |
| Two-Shot         | XGBoost (R²=0.866) | Gradient Boosting (R²=0.950) | Gradient Boosting (R²=0.801) |

### Feature Importance (SHAP Analysis):
- **Model Size** and **Token Similarity** consistently ranked highest.
- **Country Similarity** demonstrated strong relevance for performance in low-resource settings.
- **Instruction Tuning Data** had minimal impact.

---

## Conclusion

Our study provides actionable insights for enhancing multilingual language models, particularly for low-resource languages. By focusing on **token similarity** and **country similarity**, alongside traditional factors like model size and data availability, we can bridge the performance gap for underrepresented languages.

---

## Authors
- **[Sina Bagheri Nezhad](https://sinaai.github.io/)**
- **[Ameeta Agrawal](https://web.cecs.pdx.edu/~ameeta/)**
- **[Rhitabrat Pokharel](https://rhitabrat.github.io/)**
