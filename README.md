# COMPP FS24 - AI Music Generation from text messages in the style of System of a Down


## Project Overview

The main goal of this project was to generate a song where the lyrics, derived from text conversations, are sung in the distinctive style of System of a Down. This process involved several stages, from exploring existing AI tools to finetuning models to suit the specific music style of the band.

### 1. Exploring Existing AI Tools

Initially, I researched various AI tools to understand what was available for tasks like text-to-speech (TTS), music generation, and singing synthesis. While TTS and inference tools are widely available as open-source options, high-quality music generation and singing synthesis from text presented significant challenges within the project's timeframe, especially because a crucial part of this project is getting the voice to match the music.

### 2. Generating the Initial Music

To overcome these challenges, I opted to use Suno for generating music. This tool allowed me to convert text conversations directly into music, ensuring that the vocals matched the speed, harmony, and accentuation of the instrumental. The generated song included both vocals and instrumental parts. However, other than belonging to the Metal genre, they had nothing to do with the iconic sound of System of a Down. In order to achieve this I would have to tweak both the instrumental and the vocals.

### 3. Separating Vocals and Instrumental 

In order to use all the open-source tools I found during my research, I had to split the vocals and intrumental from the generated song. I utilized another AI tool called UVR5 to separate the generated song into its vocal and instrumental components. This allowed me to create the input for the models I finetuned.

### 4. Fine-Tuning AI Models

With the separated components in hand, I fine-tuned two separate AI models:
- **Vocal Models**: Customized to replicate the vocal style of Serj Tankian, the lead singer of the Band.
- **Instrumental Model**: Tailored to match the instrumental style of the band.



### 5. Reconstructing the Final Song

Finally, I replaced the initially generated content with the fine-tuned vocals and instrumental parts. Using audio editing tools, I stitched these components back together to form a cohesive song snippet.

## Conclusion
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
