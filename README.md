# EssAI: AI-generated essays detector

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Files](#files)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Model Details](#model-details)
7. [Dataset](#dataset)
8. [Fine-tuning](#fine-tuning)
9. [Results](#results)
10. [Additional Resources](#additional-resources)
11. [License](#license)
12. [Contact](#contact)

## Overview

This project fine-tunes a Large Language Model (LLM) in order to detect AI-generated essays. The model aims to help educators, researchers or individuals identify text that has been generated by AI, ensuring the authenticity of written content. You can find the full model uploaded to [Hugging Face](https://huggingface.co/diegovelilla/EssAI) since I ran into some problems with Github's LFS restrictions trying to upload it here.

## Features

- Detects AI-generated essays with very high accuracy (over 95%).
- Fine-tuned on massive dataset combining ~500K human-written and AI-generated essays.

## Files

### `requirements.txt`
This file lists all the Python packages required to run the project. It ensures that all necessary dependencies are installed for the project to function correctly.

### `essai_user_input.py`
This script is responsible for handling user inputs. Just copy in your essay and run it to get the prediction.

### `training.py`
This script has handled the training process of the model. It includes code for loading the dataset, fine-tuning it and saving the trained model.

### `testing.py`
This script is used to evaluate the performance of the trained model. It loads the test dataset, performs predictions, and calculates performance metrics such as accuracy and F1-score.

### `data_insights.py`
This script generates insights and visualizations from the data used in this project. It includes functions for analyzing dataset statistics, plotting graphs, and summarizing key data points to help understand the dataset better.

## Installation

To install the required dependencies, clone the repository and install the necessary Python packages in the **requirements.txt** file:

```bash
git clone https://github.com/diegovelilla/EssAI
cd EssAI
pip install -r requirements.txt
```

## Usage

You can use the model to check your own essays by running the **essai_user_input.py** file and coping the text into the input part right after the imports:

```python
# --- INPUT ---

input_list = [""" WRITE HERE YOUR FIRST ESSAY """,
              """ WRITE HERE YOUR SECOND ESSAY """]

# -------------
```
As you can see, you can check more than one essay at a time. This model has been trained with 350-400 word long essays, so just keep that in mind when using it. Learn more about the data used in the [data_insights](https://github.com/diegovelilla/EssAI/blob/main/essai_data_insights.ipynb) notebook.

## Model details
The base model selected for this project was the [bert-base-uncased](https://huggingface.co/google-bert/bert-base-uncased) model from hugging face. BERT (Bidirectional Encoder Representations from Transformers) is a transformer model developed and published in 2018 by Google's AI Reasearch Team. This is an open-source model with 110M parameters pretrained on a large corpus of English written data with the objectives of:

- Predicting missing words in a sentence.
- Guessing if two sentences were next to each other in the original text.

Which makes it a really competent text classification model and a great candidate for our project.

## Dataset
The dataset used was taken from Kaggle and can be found [here](https://www.kaggle.com/datasets/shanegerami/ai-vs-human-text). It contains about 500K different essays with around 60% being human written and the 40% left AI-generated. For further data info, check out the [data_insights](https://github.com/diegovelilla/EssAI/blob/main/essai_data_insights.ipynb) notebook. Also check out the [training](https://github.com/diegovelilla/EssAI/blob/main/essai_training.ipynb) and [testing](https://github.com/diegovelilla/EssAI/blob/main/essai_testing.ipynb) notebooks if interested in how the model was fine-tuned or want to check the model's performance (instructions inside).

## Fine-tuning
For resource issues and since this was intended as a learning project, only 1% from de full 500K dataset has been used which would still mean a training dataset of 4.000 essays and a testing dataset of 1.000 essays. 

I encourage anyone reading this to try to further train this model increasing the data used with the [training](https://github.com/diegovelilla/EssAI/blob/main/essai_training.ipynb) notebook.

## Results
For the first 1.000 datasets tested, the model showed a 98% accuracy. For the second one, and with a testing sample of 20.000 essays, the accuracy shown was 97%.
Further testing can be done using the [testing](https://github.com/diegovelilla/EssAI/blob/main/essai_testing.ipynb) notebook

In the initial testing phase with a sample of 1.000 essays, the model demonstrated an impressive accuracy of 98%. In a subsequent, more extensive test involving 20.000 essays, the model maintained a high accuracy of 97%. 

For more detailed evaluation and further testing, please refer to the [testing](https://github.com/diegovelilla/EssAI/blob/main/essai_testing.ipynb) notebook.

## Additional Resources

Throughout the development, I've found some resources very useful that I would like to share apart from others related to the project.

### Tutorials and Documentation

- **[Hugging Face NLP Course](huggingface.co/learn/nlp-course/)**: Comprehensive tutorials and documentation on what is NLP and how to use Hugging Face's libraries.
- **[Hugging Face Transformers Documentation](https://huggingface.co/transformers/)**: The official documentation for the Transformers library.

### Articles and Papers

- **[BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)**: The original research paper on BERT, which provided insights into the architecture and capabilities of the model.
- **[A Comprehensive Guide to Fine-Tuning BERT](https://towardsdatascience.com/a-comprehensive-guide-to-fine-tuning-bert-for-nlp-tasks-39ef4a51c7d3)**: An article that outlines various techniques for fine-tuning BERT models for specific tasks.

### Tools and Libraries

- **[Kaggle Datasets](https://www.kaggle.com/datasets)**: Platform used to source the dataset for this project.
- **[Git Large File Storage (LFS)](https://git-lfs.github.com/)**: Tool used for managing large files in the Git repository. Very useful for moving big files like the ones that form the model.

### YouTube channels

- **[Andrej Karpathy](https://www.youtube.com/@AndrejKarpathy)**: One of my favourite ML/DL YouTube channels with amazing videos. Can't stress enough how much I have learned from this man.
- **[DotCSV](https://www.youtube.com/@DotCSV)**: The first AI related YouTube channel I did ever follow. Great spanish speaking channel to keep up with AI news.

These resources provided valuable information and tools throughout the project's development. If you’re working on similar projects, they might be helpful to you as well.

## License
This project is licensed under the **Apache 2.0 License**. See the [LICENSE](https://github.com/diegovelilla/EssAI/blob/main/LICENSE) file for more details.

## Contact

For any questions or feedback please reach out to:

- **Email**: [diegovelillarecio@gmail.com](mailto:diegovelillarecio@gmail.com)
- **GitHub Profile**: [diegovelilla](https://github.com/diegovelilla)
- **Hugging Face Profile**: [diegovelilla](https://huggingface.co/diegovelilla)
- **LinkedIn**: [Diego Velilla Recio](https://www.linkedin.com/in/diego-velilla-recio/)

Feel free to open an issue on GitHub or contact me in any way if you have any queries or suggestions.
