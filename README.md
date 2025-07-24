# phi-2-chat

**A fine-tuned version of Microsoft's Phi-2 (2.7B) for conversational AI, trained on UltraChat and other datasets.**

[![Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Open%20in%20Hub-blue)](https://huggingface.co/Irfanuruchi/phi-2-chat)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.txt)

## Overview  
`phi-2-chat` is a fine-tuned variant of Microsoft's [Phi-2](https://huggingface.co/microsoft/phi-2) (2.7B parameters) optimized for dialogue tasks. Key features:

- **Base Model**: Phi-2 (2.7B parameters, MIT licensed).  
- **Training Data**: Primarily [UltraChat](https://github.com/thunlp/UltraChat) with additional datasets.
- **Capabilities**: Chatbots, instruction following, and open-ended conversation.

## Quick Start

Load the model from Hugging Face Hub:  

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model = AutoModelForCausalLM.from_pretrained(
    "IrfanUruchi/phi-2-chat",
    trust_remote_code=True,
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained("Irfanuruchi/phi-2-chat")
```

**Example chat prompt**:

```python
input_text = "<|user|>Explain quantum computing<|assistant|>"
inputs = tokenizer(input_text, return_tensors="pt").to("cuda")
outputs = model.generate(**inputs, max_new_tokens=200)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```


## License

- Model Weights: MIT (inherited from Phi-2).
- Datasets: Respective licenses apply (e.g., UltraChat is CC-BY-NC-4.0).


## Ethical considerations 

**Bias & Safety:** Fine-tuned models may inherit biases from training data.
**"Non commercial use"**

## Contributing 

Pull requests are welcome! For major changes, open an issue first.
