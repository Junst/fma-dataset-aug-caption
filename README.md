# FMA-CLAP Caption Augmentation Dataset

You can download in HuggingFace Link : [FMA-CLAP Caption Augmentation Dataset](https://huggingface.co/datasets/solbon1212/fma-dataset-aug-caption)

## Overview
This dataset is an enhanced version of the **FMA (Free Music Archive) dataset**, where we have augmented the original metadata with **natural language captions** generated using the **CLAP (Contrastive Language-Audio Pretraining) model**. The captions describe the genre, style, mood, and instrumentation of each track, making it more suitable for **zero-shot learning, music classification, and text-to-music generation tasks**.


## Dataset Details
- **Original Dataset**: [FMA: A Dataset For Music Analysis](https://github.com/mdeff/fma)
- **Augmented with**: LAION-CLAP (HTSAT-base)
- **Generated Metadata**:
  - Style and mood descriptions
  - Instrumentation details
  - Genre tagging

## How Captions Were Generated
1. **Audio Embedding Extraction**: Using CLAP, we extracted embeddings for each audio file.
2. **Candidate Selection**: A set of predefined textual descriptions for styles, instruments, and genres were used as candidates.
3. **Zero-Shot Similarity Matching**: We computed the cosine similarity between audio embeddings and text candidates, selecting the best-matching description.
4. **Final Augmentation**: The selected captions were merged with the genre metadata from the original FMA dataset.

## How to Use

### 1. Clone the Dataset from Hugging Face
```bash
git clone https://huggingface.co/datasets/YOUR_HF_DATASET_PATH
cd YOUR_HF_DATASET_PATH
```

### 2. Change the path to the FMA Dataset Directory
Ensure the dataset is placed in the correct directory where your FMA dataset is stored.


## Example Data Format
```json
{
    "id": "000002.mp3",
    "path": "/datasets/fma_small/000/000002.mp3",
    "prompt": "A storytelling rap song with introspective lyrics and soulful samples. Hip-Hop",
    "custom_metadata_module": "/configs/dataset_configs/custom_metadata/custom_md_example.py"
}
