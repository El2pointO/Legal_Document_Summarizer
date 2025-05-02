
# 🧾 Legal Case Summarizer using T5

This project demonstrates how to fine-tune a **T5 Transformer model** for **legal document summarization**, specifically court case texts. The goal is to convert lengthy legal texts into short, concise summaries to aid in downstream tasks like classification or retrieval.

## 🚀 Project Overview

Legal documents are often long and complex. This summarization model helps:
- Reduce input length for downstream ML tasks
- Improve clarity and accessibility
- Act as a preprocessing step for classification models

## 📦 Dataset

We used a cleaned version of an **Indian Legal Dataset** containing:

- `Text`: Full court case description
- `Summary`: Human-written or derived summary (target)

Make sure your dataset has these columns in your CSV:

```csv
Text, Summary
"Full case description...", "Short summary..."
```

## 🔧 Project Structure

```bash
.
├── summarizer.py             # Training and inference pipeline
├── data/
│   ├── train.csv             # Training data
│   └── test.csv              # Test data
├── outputs/                  # Saved model checkpoints and results
├── requirements.txt          # Required Python packages
└── README.md
```

## 🧠 Model Details

We fine-tune the `t5-small` model from HuggingFace Transformers:

- `max_input_length = 512`
- `max_target_length = 128`
- Optimizer: AdamW
- Epochs: 3
- Batch size: 4 (adjust based on your hardware)

## 🛠️ Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/El2PointO/legal-case-summarizer.git
cd legal-case-summarizer
```

### 2. Create a virtual environment (optional but recommended)

```bash
python -m venv venv
source venv/bin/activate  # on Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Install `accelerate` if needed

```bash
pip install accelerate
```

## 🏋️‍♂️ Training

Modify and run the training script:

```bash
python summarizer.py
```

## 🧪 Inference

After training, you can generate summaries like this:

```python
summary = summarize("Your long legal case text goes here...")
print(summary)
```

Make sure you load the trained tokenizer and model correctly in your script.

## 📈 Results

Sample output:

**Input:**
> "The petitioner seeks bail in a criminal matter involving..."

**Summary:**
> "Petitioner requests bail in a criminal case."

## 📚 Future Work

- Integrate with classification models using the summaries
- Evaluate with ROUGE and BLEU scores
- Experiment with larger T5 variants (T5-base, T5-large)
- Fine-tune on multilingual legal documents

## 🤝 Contributions

Feel free to open issues or pull requests if you improve the summarizer, add datasets, or optimize training.

## 📜 License

This project is licensed under the MIT License.

## ✍️ Author

**Lalit Kumar Ediga**  
[LinkedIn](https://www.linkedin.com/in/lalith-kumar-ediga/)  
Email: lalith.lk2509@gmail.com
