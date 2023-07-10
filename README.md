# Caption-Studio
Caption-Studio: Unleash the power of cutting-edge language models and image recognition to effortlessly generate captivating captions for your images. Elevate your social media game with expertly crafted, attention-grabbing captions that perfectly complement your visuals.
![Screenshot (756)](https://github.com/ayush-vatsal/Caption-Studio/assets/57457066/4c87ed62-c5d0-463a-b5c5-af479f397d06)
![Examples (1)](https://github.com/ayush-vatsal/Caption-Studio/assets/57457066/9dc2a8bb-eb7d-4748-8f68-e28be5ee050f)

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Models](#models)
- [Dataset](#dataset)
- [License](#license)

## Features

- **Vision Transformer**: The system leverages a state-of-the-art Vision Transformer model 'Git large' to extract meaningful descriptions from images.
- **Decoder-only Language Model**: The captions are generated using a fine-tuned Decoder-only Language Model Falcon 7B Instruct(LLM), ensuring high-quality and creative output.
- **Social Media-Worthy Captions**: The Falcon model was finetuned using a subset of the flickr dataset annotated using a larger LLM, the generated captions are specifically tailored to be suitable for sharing on social media platforms, making your posts more engaging.
- **Code and Resources**: This repository provides the necessary code and pre-trained models to get started quickly and also a demo notbook for inference with a gradio UI..

## Installation

1. Clone this repository: git clone https://github.com/ayush-vatsal/Caption-Studio.git
2. Install the required dependencies. It is recommended to use a virtual environment to avoid conflicts:
    - cd caption-studio
    - python -m venv venv
    - source venv/bin/activate # On Windows, use "venv\Scripts\activate"
    - pip install -r requirements.txt -- installing dependencies can be skipped if running any of the ipynb notebooks, they have bash scripted installs in the first code block.
4. Run the caption generator on your own images or integrate it into your project.

## Usage
To use the Caption Studio, if you have a local GPU that can handle inferencing from Falcon 7B follow these steps:
run the AI_Image_captions_for_Social_Media.ipynb notebook locally and scroll down to the very end for inference.
or, go to the AI_Image_captions_for_Social_Media.ipynb notebook, and click on open in colab. Go to runtime, click run all and scroll down to the very end for the UI, here you can upload any image and get captivating captions for your images. 

## Models
A sharded Falcon 7B instruct model was used as the base llm [Falcon-7b-instruct-sharded](https://huggingface.co/vilsonrodrigues/falcon-7b-instruct-sharded)
This model was finetuned using the PEFT library with Quantization and Low Rank Adaptation (QLoRA), the adapter for this model is here [Falcon-adapter](https://huggingface.co/ayush-vatsal/caption_qlora_finetune).
The vision transformer used for image to desciption is [Git Large COCO](https://huggingface.co/microsoft/git-large-coco)

## Dataset
To finetune the LLM we needed data that had two columns, the image descriptions (expected out of ViT) and corresponding captions. Due to the unique nature of this dataset, we had to create our own data. A subset of the flickr dataset was used to extract image descriptions (flickr dataset is used to train Vision Transformers).
These image descriptions were then annotated for captions using OpenAI's chat models. 
The datset is uploaded here [captions datset](https://huggingface.co/datasets/ayush-vatsal/description_to_caption)

## License
The datset is uploaded here[captions datset](link_here)
