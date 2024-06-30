

<div align="center">
 <img src="https://cdn-uploads.huggingface.co/production/uploads/65ec00afa735404e87e1359e/u5qyAgn_2-Bh46nzOFlcI.png">
 <h2>Accessible and portable generative AI solutions for developers and businesses.</h2>
 </div>

***Description***

"Bella-1-8b" by Cognitivess is a text generation model tailored for empathic AI interactions, supporting both English and Romanian languages. 
The model, built on the transformers architecture, features 8.03 billion parameters , well-suited for a variety of text generation tasks, including question answering, summarization, reasoning, dialogue, sentiment analysis. 
It employs a floating-point 32 (F32) tensor type for operations, facilitating speech-to-speech applications. 
Licensed under Cognitivess AI, Bella-1-8b is available on the Hugging Face platform for wide accessibility.

https://huggingface.co/cognitivess/bella-1-8b


***Under the Cognitivess Open Model License, Cognitivess AI confirms:***
- Models are commercially usable. 
- You are free to create and distribute Derivative Models. 
- Cognitivess does not claim ownership to any outputs generated using the Models or Derivative Models.

### Intended use

Bella-1-8B is a multilingual chat model designed to support a variety of languages including English, Romanian, Spanish, French, German, and many more, intended for diverse language applications.


**Model Developer:** Cognitivess AI

**Model Dates:** Bella-1-8b was trained between September 2023 and Jun 2024.

**Data Freshness:** The pretraining data has a cutoff of June 2024. Training will continue beyond the current data cutoff date to incorporate new data as it becomes available.


### Model Architecture:

Bella-1-8B model architecture is Transformer-based and trained with a sequence length of 8192 tokens.


![image/png](https://cdn-uploads.huggingface.co/production/uploads/65ec00afa735404e87e1359e/lRoj8I0Ro3OmoUOh7Lqu1.png)

**Architecture Type:** Transformer (auto-regressive language model)



Try this model on [bella.cognitivess.com](https://bella.cognitivess.com/) now.


![image/png](https://cdn-uploads.huggingface.co/production/uploads/65ec00afa735404e87e1359e/CQeAV4lwbQp1G8H5n4uWx.png)


# Usage

```python

from transformers import AutoModelForCausalLM, AutoTokenizer
import torch

model_path = "cognitivess/bella-1-8b"

# Load the tokenizer and model, converting model to half precision
tokenizer = AutoTokenizer.from_pretrained(model_path)
model = AutoModelForCausalLM.from_pretrained(model_path).half().eval()

# Move the model to CUDA if available
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model.to(device)

# Prompt content: "hi"
messages = [
    {"role": "user", "content": "Who are you?"}
]

input_ids = tokenizer.apply_chat_template(conversation=messages, tokenize=True, add_generation_prompt=True, return_tensors='pt')

# Move input_ids to the same device as the model
input_ids = input_ids.to(device)

# Adjust the generate method to set max_new_tokens
output_ids = model.generate(input_ids, max_new_tokens=50)

response = tokenizer.decode(output_ids[0][input_ids.shape[1]:], skip_special_tokens=True)

# Model response: "I'm Bella, an AI model developed by Cognitivess."
print(response)


```

**Evaluation results**
**The model bella-1-8b achieves the following results:**
![image/png](https://cdn-uploads.huggingface.co/production/uploads/65ec00afa735404e87e1359e/VTsxSAOGiOx0yS-UK3RkL.png)

**Safety**
bella-1-8b can make mistakes. Check important info.

**Contact:**
<a href="mailto:hello@cognitivess.com">hello@cognitivess.com</a>


![image/png](https://cdn-uploads.huggingface.co/production/uploads/65ec00afa735404e87e1359e/u5qyAgn_2-Bh46nzOFlcI.png)
