# LLAMA-Tree-of-Thoughts Colab Notebook

This Colab notebook is a small experimentation based on the code from `rhohndorf`, and you can find the original repository [here](https://github.com/rhohndorf/LLaMa-ToT/tree/main).

## Requirements

To run this notebook, you will need the following:

- A Colab environment (either free or paid version)
- Internet connectivity

## Installation

To get started, we need to install the `llama-cpp-python` library. Run the following command:

```python
!pip install llama-cpp-python
```

## Model Download

Next, we will download the LLAMA model file. The model file contains the pre-trained LLAMA reasoning model. Run the following code block:

```python
import requests

url = "https://huggingface.co/TheBloke/Wizard-Vicuna-7B-Uncensored-GGML/resolve/main/Wizard-Vicuna-7B-Uncensored.ggmlv3.q4_1.bin"
filename = "modelFile.bin"

response = requests.get(url)
response.raise_for_status()

with open(filename, "wb") as file:
    file.write(response.content)

print("File downloaded successfully!")
```

## LLAMA Settings

Before running the LLAMA experiment, we need to configure the LLAMA settings. Modify the settings according to your preferences in the following code block:

```python
cfg_model_path = "/content/modelFile.bin"  # Path to the downloaded model file
cfg_temperature = 0.7  # Temperature parameter for LLAMA's text generation
cfg_context_size = 2048  # Context size for LLAMA's reasoning

cfg_branching_factor = 3  # Branching factor for LLAMA's planning phase
cfg_max_plan_length = 3  # Maximum plan length for LLAMA's planning phase
```

## Running the LLAMA Experiment

To run the LLAMA experiment, execute the code block below:

```python
from llama_cpp import Llama

llm = Llama(cfg_model_path, n_ctx=cfg_context_size)

# Define helper functions and solve the problem
# ...

# Main execution
# ...
```

Ensure that you have completed the necessary modifications in the code block above before running the experiment. Replace the placeholder goal with your desired problem statement:

```python
goal = "Earn money online without finding clients"
```

The notebook will then proceed to find a plan that solves the given goal. The plan will be displayed as the output.

Enjoy experimenting with LLAMA-Tree-of-Thoughts in this Colab notebook!
