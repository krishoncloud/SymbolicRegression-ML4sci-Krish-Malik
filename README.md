# SymbolicRegression-ML4Sci-Krish-Malik

## Tasks & Results
Evaluation Metric: Sequence accuracy was used to measure model performance, ensuring that predicted symbolic expressions exactly match the ground truth.

###  Common Task 1: Preprocessing & Tokenization
- **Objective:** Prepare and tokenize equations to make them suitable for symbolic regression using machine learning models.
- **What I Did:**
  - **Dataset Cleaning & Structuring:** Converted raw symbolic expressions into a structured dataset.
  - **Tokenization:**
    - Used a custom tokenizer to convert mathematical equations into machine-readable tokens.
    - Ensured a consistent representation across the dataset to maintain integrity.
  - **Preprocessing Checks:** Verified token distribution and equation complexity to avoid bias.
- **Outcome:** Successfully prepared and tokenized dataset, making it ready for transformer-based models.

---

### Common Task 2: Basic Transformer Model
- **Objective:** Implement and train a baseline Transformer model for symbolic regression to establish a performance benchmark.
- **What I Did:**
  - Implemented a Transformer Encoder for sequence-to-sequence learning.
  - **Trained on Preprocessed Data:** Used standard hyperparameters without specialized optimization.
  - **Evaluated Model Performance:**
    - Checked token-wise accuracy to ensure correct mathematical expression formation.
    - Compared predictions with ground truth symbolic equations.
- **Results:** **80% Accuracy**
- **Key Takeaways:**
  - The model learned symbolic representations well, but there was room for improvement in sequence coherence.
  - Hyperparameter tuning and specialized attention mechanisms could improve accuracy.

---

### Task 3.3: Mixture of Experts (MoE) Transformer
- **Objective:** Enhance transformer performance by integrating a Mixture of Experts (MoE) model for better efficiency and specialization.
- **What I Did:**
  - **Implemented MoE:**
    - Divided computations across multiple expert layers.
    - Used a gating mechanism to dynamically select experts for specific token sequences.
  - **Experimental Additions:**
    - **Flash Attention:**
      - Tried optimizing attention efficiency for long sequences.
      - **Issue:** Since the token lengths in our dataset were relatively short, Flash Attention caused instability and led to lower accuracy.
    - **KAN (Kolmogorov-Arnold Networks):**
      - Explored the idea of using KAN layers for more structured symbolic representation.
      - **Limitation:** Token constraints made its integration infeasible in the current architecture.
- **Results:** **84% Accuracy** (Improved from 80%)
- **Key Takeaways:**
  - MoE helped improve accuracy by allowing specialized layers to focus on different mathematical structures.
  - Flash Attention was not beneficial due to token length constraints.
  - KAN integration was not viable in this setup.

---

### Task 3.5: Genetic Algorithm (GA) for Hyperparameter Tuning
- **Objective:** Use Genetic Algorithms (GA) to optimize hyperparameters for better model performance.
- **What I Did:**
  - **Implemented a Genetic Algorithm Optimization Pipeline:**
    - Defined search space (embed_dim, num_heads, learning rate, etc.).
    - Used mutation & crossover to generate new hyperparameter combinations.
    - **Selection criteria:** Models were evaluated based on accuracy, and the best-performing configurations were carried forward.
  - **Fixed Model Constraints:**
    - Ensured embed_dim was divisible by num_heads to avoid architecture errors.
    - Avoided configurations that caused instability in training.
- **Key Performance Improvements:**
  - Hyperparameter tuning improved transformer efficiency by optimizing learning rate and attention mechanisms.
  - Significant accuracy boost compared to baseline models.
- **Results:** **91.5% Accuracy ** (Improved from 84%)
- **Key Takeaways:**
  - GA provided an automated way to fine-tune hyperparameters, leading to major performance gains.
  - Addressed architecture constraints dynamically, ensuring valid configurations.
  - Further improvements could be explored using Neuroevolution or Evolution Strategies (ES).

---

## Model Performance Summary
| Model | Approach | Accuracy (%) |
|---|---|---|
| **Basic Transformer** | Standard Transformer (Baseline) | **80%** |
| **MoE Transformer** | Mixture of Experts (MoE) | **84%** |
| **GA-Optimized Transformer** | Transformer + Genetic Algorithm | **91.5%** |
