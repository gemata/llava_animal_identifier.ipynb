# 🦁 Animal Identifier using LLaVA-7B

This project demonstrates the power of Vision-Language Models (VLM) for accurate animal identification using the **LLaVA-1.5 7B** model, optimized for efficiency via quantization.

## 🚀 Project Overview

The project utilizes `transformers`, `bitsandbytes`, and `accelerate` to load the **llava-hf/llava-1.5-7b-hf** model from the Hugging Face Hub. To reduce VRAM requirements and enable execution in environments like Google Colab, **4-bit Quantization** (`BitsAndBytesConfig`) is applied.

### Key Features:
- **Model:** LLaVA-1.5 7B (Large Language and Vision Assistant).
- **Optimization:** 4-bit Quantization for speed and memory efficiency.
- **Prompt Engineering:** A strict instruction set that forces the AI to:
  - Return answers strictly in JSON format (`{"animal": "Exact_Common_Name"}`).
  - Avoid vague guesses (e.g., "bird", "mammal").
  - Identify the species as precisely as possible (e.g., "Red Fox" instead of just "Fox").
- **Source:** Model loaded directly from [Hugging Face Hub](https://huggingface.co/llava-hf/llava-1.5-7b-hf).

## ⚙️ Installation & Setup

To run this notebook, you need the following libraries:

```bash
!pip install -q -U transformers accelerate bitsandbytes pillow matplotlib
```
### 🔑 How to Get Your Hugging Face Token

To access the LLaVA model, you need a free Hugging Face account and an API token. Follow these steps:

1. **Create an Account:** Go to [Hugging Face](https://huggingface.co/) and sign up if you haven't already.
2. **Accept Terms:** Visit the [LLaVA-1.5-7B Model Page](https://huggingface.co/llava-hf/llava-1.5-7b-hf) and click **"Agree"** to accept the usage terms.
3. **Generate Token:**
   - Go to your [Settings > Access Tokens](https://huggingface.co/settings/tokens).
   - Click **"New Token"**.
   - Give it a name (e.g., `colab-token`).
   - Select permission type: **Read** (this is sufficient for downloading models).
   - Click **"Generate"** and copy the token (starts with `hf_...`).
4. **Use in Colab:**
   - In Google Colab, go to the left sidebar, click the **Key icon** (Secrets), and add a new secret named `HF_TOKEN`. Paste your token there.
   - *Alternatively*, you can paste it directly in the code cell where indicated (though using Secrets is more secure).
<img width="1019" height="735" alt="image" src="https://github.com/user-attachments/assets/2c55f8bf-686b-47bb-a563-c65bdcce0e6f" />
<img width="1077" height="859" alt="image" src="https://github.com/user-attachments/assets/e5f37878-5032-4998-bc34-66aa3ce42fa4" />
<img width="1070" height="854" alt="image" src="https://github.com/user-attachments/assets/da915501-f040-460b-8d1f-d512ae61e69d" />
