# Emotion Detection using Fine-Tuned BERT

## Introduction
This project fine-tunes a BERT model to classify emotions in text.  
It uses the Hugging Face `emotion` dataset with six emotion classes: joy, sadness, anger, fear, love, and surprise.  
The model can be used to detect emotions from sentences, useful for chatbots, mental health applications, and content moderation.

---

## Dataset and Problem
The dataset contains about 20,000 English sentences labeled with six emotions.  
The task is multi-class classification to assign one of these emotions to each sentence.  
Data was split into training (80%), validation (10%), and test (10%) sets.

---

## Model Design and Training
- Pretrained `bert-base-uncased` model used.  
- Added a classification head with six outputs (one per emotion).  
- Handled class imbalance using weighted cross-entropy loss.  
- Tokenized sentences with padding and truncation for uniform input length.  
- Trained for 4 epochs, batch size 16, learning rate 5e-5.  
- Used validation set for early stopping and checkpointing best model.

---

## Results & Evaluation

| Emotion  | Precision | Recall | F1-score |
| -------- | --------- | ------ | -------- |
| Sadness  | 0.98      | 0.95   | 0.96     |
| Joy      | 0.99      | 0.90   | 0.94     |
| Love     | 0.74      | 0.97   | 0.84     |
| Anger    | 0.90      | 0.97   | 0.93     |
| Fear     | 0.92      | 0.85   | 0.88     |
| Surprise | 0.65      | 0.94   | 0.77     |

- **Overall accuracy:** 92.5%  
- **Macro F1-score:** 89%  

The model performs well on frequent emotions like joy and sadness, and reasonably on less frequent ones. Surprise emotion is the hardest to classify accurately.

---

## Example Predictions
- *"I am so happy today!"* → Joy  
- *"I feel angry about what happened."* → Anger  
- *"She looks very sad and down."* → Sadness  

Predictions are consistent and demonstrate good generalization.

---

## Reflection and Future Work
- Class imbalance was addressed with weighted loss, but rare emotions like surprise still need improvement.  
- Future improvements: data augmentation, multilingual models, multimodal emotion recognition (text + speech + facial expressions).  

---

## References
- Gao, T., Fisch, A., Chen, D. (2021). Making pre-trained language models better few-shot learners. ACL.  
- Houlsby, N., et al. (2019). Parameter-efficient transfer learning for NLP. ICML.  
- Lester, B., Al-Rfou, R., Constant, N. (2021). The power of scale for parameter-efficient prompt tuning. EMNLP.  
- Li, X.L., Liang, P. (2021). Prefix-tuning: Optimizing continuous prompts for generation. ACL.  
- Scao, T.L., Rush, A.M. (2021). How many data points is a prompt worth? arXiv.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.
