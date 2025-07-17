# AI Perf: DaCapo Benchmark Q&A

A fine-tuned DeepSeek-Coder-6.7b-instruct model for answering questions about DaCapo benchmark suites.

## Results
Ongoing efforts to improve factual accuracy and reduce repetition in generated responses. Current challenges include severe overfitting due to limited training data, though training optimizations like early stopping are implemented.

### Current Inference Status
* **Hardware:** Local GPU (running 4-bit quantized model)
* **Inference Time:** ~15 seconds per query (optimized with `use_cache=True`)
* **Challenges:** Still experiencing factual inaccuracies, repetition, and unwanted conversational turns in output due to data scarcity.

## How to Run

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/phdiep2003/ai-perf-qa
    ```
2.  **Install Dependencies:**
    Ensure you have all required libraries installed. You can use:
    ```bash
    pip install torch transformers peft datasets tensorboard accelerate
    ```
    *(Note: For specific PyTorch/CUDA versions, check pytorch.org for optimal `torch` installation.)*

3.  **Prepare Training Data:**
    Ensure your `dacapo_train.jsonl` file is in the project directory, containing your formatted Q&A pairs for fine-tuning.

4.  **Run the Notebook/Script:**
    Open `AI for Benchmark.ipynb` (or your Python training script) in Jupyter or VS Code, and run all cells to train the model and perform inference.