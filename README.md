# LocalGPT

LocalGPT is a fully localized natural language processing tool built with Hugging Face's Transformers library in Python. It allows you to generate text, fine-tune models, and is designed to run on your local machine, ensuring complete privacy as no data leaves your network or computer.

## Installation

Before you start, ensure you have Python installed on your machine. If not, download it from the [official Python website](https://www.python.org/downloads/).

1. **Clone the Repository**

    Open your command prompt or terminal and navigate to the directory where you want to clone the repository. Use the following command to clone the repository:

    ```bash
    git clone https://github.com/BjornMelin/LocalGPT.git
    ```

2. **Set Up a Virtual Environment (Optional)**

    It's a good practice to set up a virtual environment to isolate your project and its dependencies from other projects. Use the following commands to create and activate a virtual environment:

    ```bash
    python -m venv .venv
    .venv\Scripts\activate
    ```

3. **Install Dependencies**

    Navigate to the cloned repository directory and install the necessary libraries using pip:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Load the Model**

    You can load the GPT-2 model using the following Python code:

    ```python
    from transformers import GPT2LMHeadModel, GPT2Tokenizer

    tokenizer = GPT2Tokenizer.from_pretrained("gpt2")
    model = GPT2LMHeadModel.from_pretrained("gpt2")
    ```

2. **Generate Text**

    Here's a simple way to generate text:

    ```python
    input_text = "Once upon a time"
    inputs = tokenizer.encode(input_text, return_tensors="pt")
    outputs = model.generate(inputs, max_length=500, num_return_sequences=1, no_repeat_ngram_size=2)
    generated_text = tokenizer.decode(outputs[0], skip_special_tokens=True)
    print(generated_text)
    ```

3. **Train Your Model**

    If you want to fine-tune the model on your own data, you'll need to train it. This requires a dataset and some time, depending on the size of the dataset and the capabilities of your computer. Hugging Face provides a [script for fine-tuning](https://github.com/huggingface/transformers/tree/master/examples/language-modeling) the model.

<!-- ## Contributing

Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first. -->

## License

[MIT](LICENSE)
