# AAI-511_Music-Identifier 

# Project Introduction
Classifying composer from classical music.  Using symbolic MIDI data, comparing two deep learning architectures (LSTM and CNN). 

## Team 6
- Evelin Bustamante
- Juan Norena
- Daniel Sims

## Overview
Experienced musicians can often detect composer based off the unique style, but this is a hard task for novice listeners. This project builds an end-to-end pipeline that parses raw MIDI files into features, trains and compares two artitectures, and evaluates both models to see how they perform.
# Result: 
The CNN outperformed the LSTM, suggesting for this feature set, short-range musical patterns are more discriminative of a composers identity than long-range dependencies.

## Repository Contents
AAI_511_Group_6_Final_Project.ipynb
Description: Full pipeline data download, preprocessing, EDA, Model Training, and Model Evaluation

## Dataset
- Source: MIDI Classic Music via Kaggle
- Raw Size: 3,929 MIDI files across 175 composers
- Filtered to 4 Target Composers: Bach, Beethoven, Chopin, Mozart

  ## Feature Extraction & Preproccessing
  Each MIDI file is parsed with pretty_midi, every note has four extracted features:
  - Pitch - MIDI note number
  - Step - time elapsed since previous note
  - Duration - length note is sustained
  - Velocity - note intensity

 ## Model Architectures
 # LSTM Classifer
 Rationale: Designed to capture long-range sequential dependencies across a musical phrase
 
 # CNN Classifer
 Rationale: Designed to capture short- range motifs, treating the note sequence as a 1D image

## How to Run
1. Open AAI_511_Group_6_Final_Project.ipynb in Google Colab (recommended) or Jupyter.
2. Run the setup cells to install dependencies (pretty_midi, pypianoroll, kagglehub) and download the dataset from Kaggle.
3. Run the preprocessing and EDA cells to build df_files, extract features, and generate the sequence dataset.
4. Run the LSTM training cell (--model lstm --epochs 15), then the CNN training cell (--model cnn --epochs 15). 
5. Run the evaluation cells to generate classification reports, confusion matrices, and the final LSTM-vs-CNN comparison.
