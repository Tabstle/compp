# COMPP FS24 - AI Music Generation in the Style of System of a Down

## Overview
This project aims to generate a song in the style of System of a Down using AI techniques. The lyrics are derived from a text conversation, and the instrumental tracks are created by fine-tuning models. This repository documents the entire process, including data preparation, model training, and final music generation.

## Project Structure
- **data/**: Contains the datasets used for training.
  - **vocals/**: Vocal tracks separated into screaming and singing.
  - **instrumental/**: Instrumental tracks.
- **notebooks/**: Jupyter notebooks used for various stages of the project.
- **results/**: Generated music and logs from the training process.
- **scripts/**: Python scripts for data downloading, preprocessing, training, and music generation.
- **assets/**: Images and other assets used in the documentation.

## Steps

### Data Preparation
1. **Vocal and Instrumental Separation**: Used UVR5 Ultimate Vocal Remover AI to separate the vocals and instrumental tracks from the Toxicity album.
2. **Dataset Creation**: Created two vocal datasets (screaming and singing) and one instrumental dataset.

### Model Training
1. **Fine-tune Riffusion**: Attempted to fine-tune Riffusion for both lyrics and instrumental but faced issues.
2. **Train Voice Models**: Used the Applio AI application to train two voice models for screaming and singing.
3. **Fine-tune MusicGen**: Fine-tuned MusicGen by Meta for generating instrumental music.

### Music Generation
1. **Generate Base Track**: Generated a base track using the fine-tuned MusicGen model.
2. **Generate Vocals**: Used Suno to generate vocals based on the text and then split it into screaming and singing using UVR5.
3. **Combine Tracks**: Edited the generated vocals and instrumental together in Reaper to match the beat.

## Usage
1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/AI-Music-Generation.git
    cd AI-Music-Generation
    ```

2. **Download Datasets**
    ```bash
    python scripts/download_datasets.py
    ```

3. **Run Notebooks**

#### Fine-tune Riffusion
[Open in Colab](https://colab.research.google.com/drive/1lWqp8TiV969vTRCxl-4jLEjVcQw3TTmh#scrollTo=NaQ3Jytoqyk5)

4. **Generate Music**
    ```bash
    python scripts/generate_music.py
    ```

## Results
The generated music tracks can be found in the `results/generated_music/` directory.

## Acknowledgements
- **UVR5 Ultimate Vocal Remover AI**
- **Applio AI**
- **MusicGen by Meta**
- **Suno**

## License
[MIT License](LICENSE)
