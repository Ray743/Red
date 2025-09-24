# AI-Powered Linux Assistant Fine-Tune Project (“Red”) 🚧 *(Work in Progress)*

This repository is an **early-stage project** to fine-tune a model into functioning as a command-line interface (CLI) assistant named **“Red”**.
Red is intended to become an AI-powered Linux assistant capable of understanding natural language, mapping it to Linux commands, and providing guidance in real-time.

⚠️ **Note:** The application is **not complete**. The dataset is still being expanded and refined, and training scripts are under active development.

---

## Current Goals

* Collect and curate Linux CLI command–response pairs.
* Build a dataset with contextual tags, tool usage, and OS compatibility.
* Prepare a training-ready structure for fine-tuning.
* Experiment with training configurations to evaluate Red’s potential.

---

## Project Structure (So Far)

```
.
├── data/
│   └── LINUX_DATASET.jsonl        # WIP dataset for fine-tuning
├── src/
│   └── train.py                   # Placeholder training script
├── configs/
│   └── finetune_config.yaml       # Initial fine-tuning config (subject to change)
├── requirements.txt               # Dependencies for training experiments
└── README.md                      # Project documentation (this file)
```

---

## Dataset (Work in Progress)

The dataset is still being collected and improved. Each record is structured as:

* **instruction**: The natural language command/query.
* **response**: The expected assistant output or explanation.
* **mission\_tag**: A category label for routing (e.g., "system", "network").
* **context**: Optional context about the system/environment.
* **tools**: Required utilities/tools (e.g., `apt`, `top`, `systemctl`).
* **os\_compatibility**: Supported distributions.
* **follow\_up**: Suggested next actions for the user.

Example (simplified):

```json
{
  "instruction": "check disk usage",
  "response": "Filesystem      Size  Used Avail Use% Mounted on...",
  "mission_tag": "system",
  "context": "User monitoring storage",
  "tools": ["df"],
  "os_compatibility": ["Ubuntu", "Debian", "Fedora"],
  "follow_up": "Suggest cleaning unused packages"
}
```

---

## Requirements

The project relies on common machine learning and NLP libraries to handle dataset preparation, fine-tuning, and evaluation:

* **tensorflow==2.10.0** → Backend deep learning framework used for training and fine-tuning.
* **transformers==4.21.1** → Hugging Face Transformers library for model architectures (e.g., GPT, BERT).
* **datasets==2.4.0** → Efficient dataset loading, splitting, and preprocessing.
* **scikit-learn==1.0.2** → Utilities for evaluation (metrics, train-test splits, preprocessing).
* **pandas==1.4.2** → Data manipulation and preprocessing for dataset curation.
* **numpy==1.21.6** → Core numerical computations used across the pipeline.
* **pyyaml==6.0** → YAML configuration file parsing (used for training configs).

Install dependencies with:

```bash
pip install -r requirements.txt
```

---

## Training (Planned)

1. Place curated dataset under `data/LINUX_DATASET.jsonl`.
2. Adjust parameters in `configs/finetune_config.yaml`.
3. Run the training script:

```bash
python src/train.py
```

*(Training scripts and configs are experimental and may change as the project evolves.)*

---

## Next Steps

* Expand dataset with broader coverage of Linux commands.
* Refine fine-tuning process for consistency.
* Add evaluation scripts to test command accuracy and safety.

---

## Contributing

Contributions are welcome, but since this is still a **WIP**, the focus is on:

* Adding realistic command-response data.
* Improving dataset quality and diversity.
* Suggesting improvements to the training setup.

---

## License

This project is currently open for **educational and research purposes** only.

---
