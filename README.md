# phi-2-chat

**A fine-tuned conversational variant of Microsoft's Phi-2 (2.7B) optimized for dialogue tasks**

[![Model License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Hugging Face Hub](https://img.shields.io/badge/%F0%9F%A4%97%20Model%20Hub-Open-blue)](https://huggingface.co/Irfanuruchi/phi-2-chat)
[![GitHub Repository](https://img.shields.io/badge/🔗%20GitHub-Open-24292e)](https://github.com/IrfanUruchi/phi-2-chat)

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
