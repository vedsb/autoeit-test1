# AutoEIT — GSoC 2026 Participation Tests

This repository contains the completed evaluation tests for the **AutoEIT** project (GSoC 2026). The focus of this submission is **Test I: Audio File Transcription**.

## 🚀 Project Overview

The objective of this task is to generate high-accuracy, verbatim transcriptions of elicited imitation task (EIT) audio in Spanish. These transcriptions capture the exact production of participants, including disfluencies and learner errors, which are essential for evaluating second-language proficiency.

## 🛠️ Methodology (Test I)

- **ASR Engine**: OpenAI Whisper `medium`.
- **Target Language**: Spanish (`es`).
- **Strategy**:
  - Used word-level timestamps for precise timing.
  - Implemented 30-sentence segmentation per participant.
  - Prepended context prompts using target sentences to guide the ASR engine effectively.
  - Cleaned ASR hallucinations while preserving disfluencies (uh, um, repetitions) and errors.

## 📁 Repository Structure

- `transcribe_eit.py`: The main Python script for audio-to-text processing.
- `AutoEIT_Transcription.ipynb`: Detailed Jupyter notebook documenting the approach, challenges, and output verification.
- `AutoEIT_Transcription.html`: Exported notebook for easy viewing.
- `AutoEIT Sample Audio for Transcribing_COMPLETED.xlsx`: The final transcribed dataset.
- `raw_transcriptions/`: (Excluded from repo) Raw Whisper JSON outputs for proof of work.

## 📝 Challenges & Observations

1. **Audio Segmentation**: Identifying the boundary between the stimulus playback and the participant's response was handled using a gap-based threshold (3.0s).
2. **Participant 038012**: Addressed a 12-minute offset in the initial recording as specified in the test instructions.
3. **Disfluency Preservation**: Whisper Medium was found to be effective at retaining fillers (eh, uh), which are critical for the EIT rubric.

## 🧪 How to Run

1. Clone this repository.
2. Install dependencies: `pip install openai-whisper openpyxl torch spacy`.
3. Download the Spanish model: `python -m spacy download es_core_news_lg`.
4. Run the transcription: `python transcribe_eit.py`.

---
**Contact**: [Your Name/Email]  
**Submitted for**: AutoEIT (GSoC 2026)
