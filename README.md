# TEXT_GENERATION_MODEL

*COMPANY*: CODTECH IT SOLUTIONS PVT.LTD

*NAME*: Manvit Mahesh Deshmukh

*INTERN ID*: CT12DL764

*DOMAIN*: Artificial intelligence.

*DURATION*: 12 weeks

*MENTOR*:  Neela Santhosh Kumar

# GPT‑2 Large Interactive Text Generation - CodTech Internship Task 4

A Python script for generating coherent, topic‑based paragraphs using Hugging Face’s GPT‑2 Large model. This repository provides an easy‑to‑use interactive command‑line program that runs on GPU (if available) in Google Colab or any local environment with PyTorch and a CUDA‑enabled GPU. Just enter your prompt and watch GPT‑2 produce rich, on‑topic content.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [How It Works](#how-it-works)
6. [Configuration Options](#configuration-options)
7. [Examples](#examples)
8. [Performance Tips](#performance-tips)
9. [Contributing](#contributing)
10. [License](#license)
11. [ScreenShot](#ScreenShot)
    
---

## Project Overview

This project demonstrates how to leverage OpenAI’s GPT‑2 Large architecture via the Hugging Face Transformers library to generate coherent, human‑like paragraphs on almost any topic. Traditional LSTM‑based models require custom data collection and training for each domain. In contrast, GPT‑2 Large is pre‑trained on a massive corpus of web text, so it already understands grammar, context, and topical relevance. You simply provide a prompt, and GPT‑2 continues the text in a fluid, contextually appropriate manner.

Designed for both beginners and advanced users, this script can be run in Google Colab or any local Python environment with PyTorch. The interactive loop prompts you to enter a string, then outputs a generated paragraph of configurable length, randomness (temperature), and diversity (top‑p sampling). It supports multi‑sequence outputs, reproducibility via seed setting, and gracefully falls back to CPU if no GPU is found.

---

## Features

- **Interactive Command‑Line Interface**: Type your prompt and get immediate results.
- **GPU Acceleration**: Automatically utilizes a CUDA‑enabled GPU for faster inference.
- **Customizable Parameters**: Adjust `max_length`, `temperature`, `top_p`, and `num_return_sequences` to control output length, creativity, and variety.
- **Reproducible Outputs**: Fixed random seed ensures consistent outputs across runs when desired.
- **Pad Token Workaround**: Explicitly sets `pad_token` to `eos_token` to avoid known tokenizer issues.
- **Supports GPT‑2 Large**: More coherent and nuanced than the smaller base model.

---

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/gpt2-text-gen.git
   cd gpt2-text-gen
   ```

2. **Ensure Python 3.7+ and pip are installed**

3. **Install dependencies**

   ```bash
   pip install torch transformers --quiet
   ```

4. **(Optional) Enable GPU**

   - In Google Colab: `Runtime > Change runtime type > GPU`
   - Locally: Install CUDA toolkit and torch with CUDA support.

---

## Usage

Run the script directly from the command line or Colab cell:

```bash
python generate_text.py
```

Then follow the prompts:

```
Enter your prompt (or type 'exit' to quit):
> Future of renewable energy in rural India

📄 Generating text...

📝 Generated Paragraph:
Renewable energy adoption in rural India has accelerated over the past decade...
```

Type `exit` to terminate the interactive loop.

---

## How It Works

1. **Device Setup**: Detects CUDA availability and sets device to `cuda:0` or `cpu`.
2. **Model Loading**: Downloads and loads `gpt2-large` and its tokenizer from Hugging Face.
3. **Pad Token Fix**: Assigns `pad_token` to the end‑of‑sentence token to prevent padding errors.
4. **Seed Initialization**: Uses `set_seed(42)` for repeatable outputs.
5. **Text Generation**:
   - Encodes the user prompt into token IDs.
   - Calls `model.generate()` with sampling parameters.
   - Decodes tokens back into text and prints the result.

---

## Configuration Options

| Parameter              | Description                                                   | Default |
| ---------------------- | ------------------------------------------------------------- | ------- |
| `max_length`           | Maximum number of tokens to generate (including prompt).      | `250`   |
| `temperature`          | Sampling temperature: lower = conservative, higher = creative | `0.8`   |
| `top_p`                | Nucleus sampling probability threshold                        | `0.95`  |
| `num_return_sequences` | Number of distinct generations per prompt                     | `1`     |

Adjust these values in `generate_text()` call for different styles.

---

## Examples

- **Short factual style**:
  ```python
  generate_text("Mars colonization timeline", max_length=180, temperature=0.6, top_p=0.9)
  ```
- **Creative narrative**:
  ```python
  generate_text("A day in the life of a time-traveling cat", max_length=220, temperature=1.0, top_p=0.9)
  ```

---

## Performance Tips

- Use a **GPU** to reduce generation time from seconds to fractions of a second.
- If memory runs out with `gpt2-large`, switch to `gpt2-medium` or `gpt2`:
  ```python
  model_name = "gpt2-medium"
  ```
- Lower `max_length` or `num_return_sequences` to save GPU memory.

---

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request for:

- Adding support for other Transformer models (e.g., GPT‑Neo, GPT‑J).
- Incorporating streaming/text‑to‑speech outputs.
- Packaging as a pip installable CLI tool.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## ScreenShot

<img width="2559" height="1598" alt="Image" src="https://github.com/user-attachments/assets/ded8a1b9-883b-4be5-a9db-89cfc52514bb" />
<img width="2559" height="1599" alt="Image" src="https://github.com/user-attachments/assets/36f772c7-54e7-4c66-bb36-fbff825fd481" />
<img width="2559" height="1599" alt="Image" src="https://github.com/user-attachments/assets/c763dfee-410e-4ecd-91a3-7ffdbc6ad7d0" />
<img width="2559" height="572" alt="Image" src="https://github.com/user-attachments/assets/37d3ec46-f944-44ff-9269-2d80dcab0efd" />
