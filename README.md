## LLM Fine-Tuning Playground

This repository contains experiments and utilities for fine-tuning and evaluating LLMs (e.g. LLaMA variants) on both **math** tasks and **custom datasets**, primarily using Jupyter notebooks.

### Project Structure

- **`fine_tune_llama_math/`**
  - `tiny_Llama_math.ipynb`: end-to-end fine-tuning of a small LLaMA-style model on math-oriented data.
  - `evalution_tiny_Llama_math.ipynb`: evaluation and comparison of the math-tuned model.
- **`fine_tune_custom_data/`**
  - `custom_data_tuning.ipynb`: fine-tuning workflow on your own custom dataset.
  - `custom_data_evalution.ipynb`: evaluation of the custom-data-tuned model.

### Requirements

- Python 3.10+ (recommended)
- GPU with sufficient VRAM for the chosen model size (CUDA recommended but not strictly required for very small models)
- Recommended packages (install via `pip` or adapt to your environment):

```bash
pip install -U pip
pip install \
  torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
pip install \
  transformers \
  datasets \
  accelerate \
  peft \
  bitsandbytes \
  jupyter \
  matplotlib \
  pandas \
  scikit-learn
```

> **Note**: Adjust the PyTorch install command and CUDA version according to your hardware and OS.

### Getting Started

1. **Clone this repo**

```bash
git clone https://github.com/Darshit02/LLM-finetuning.git
cd "LLM finetuning"
```

2. **Create and activate a virtual environment (optional but recommended)**

```bash
python -m venv .venv
.venv\Scripts\activate  # on Windows
# source .venv/bin/activate  # on macOS / Linux
```

3. **Install dependencies**

Use the commands in the **Requirements** section, or create your own `requirements.txt` and run:

```bash
pip install -r requirements.txt
```

4. **Start Jupyter**

```bash
jupyter notebook
```

Then open the desired notebook:

- `fine_tune_llama_math/tiny_Llama_math.ipynb`
- `fine_tune_llama_math/evalution_tiny_Llama_math.ipynb`
- `fine_tune_custom_data/custom_data_tuning.ipynb`
- `fine_tune_custom_data/custom_data_evalution.ipynb`

### Custom Data Fine-Tuning

- Place your dataset in a convenient location (e.g. `data/` or a custom path).
- Update the dataset loading cells in `custom_data_tuning.ipynb` to point to your files.
- Ensure your data is formatted in a way that the tokenization and training cells expect (e.g. JSON/CSV with `instruction`, `input`, `output` fields or similar).

### Tips & Recommendations

- **Checkpointing**: Configure checkpoints to save into a folder like `checkpoints/` (already ignored by `.gitignore`) to avoid committing large model files.
- **Experiment tracking**: Optionally integrate tools like `wandb` or MLflow; corresponding folders are also ignored in `.gitignore`.
- **Reproducibility**: Consider fixing random seeds in the notebooks for more reproducible runs.

### License

Add your preferred license here (e.g. MIT, Apache-2.0), especially if you intend to share or open-source this project.


