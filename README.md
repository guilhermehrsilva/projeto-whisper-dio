# 🎙️ Multi-Modal Voice Assistant: Whisper & GPT Integration

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![OpenAI](https://img.shields.io/badge/OpenAI-Whisper%20%7C%20GPT-green)
![Status](https://img.shields.io/badge/Status-Prototype-orange)

## 📑 Overview
This project implements a **full-duplex conversational pipeline** integrating State-of-the-Art (SotA) Artificial Intelligence models. It bridges the gap between raw audio input and intelligent synthesis, creating a seamless voice assistant experience.

The system orchestrates three distinct AI stages:
1.  **ASR (Automatic Speech Recognition):** Utilizing OpenAI's **Whisper** model to transcribe audio with human-level accuracy across multiple languages.
2.  **LLM Reasoning:** Processing intent and context using **GPT-3.5 Turbo / GPT-4** models via the OpenAI API.
3.  **TTS (Text-to-Speech):** Synthesizing natural language responses using **gTTS** (Google Text-to-Speech) algorithms.

## ⚙️ Architecture Pipeline

```mermaid
graph LR
    A[User Audio Input] -->|MediaStream API| B(Audio Buffer)
    B -->|Preprocessing| C{Whisper Model}
    C -->|High-Fidelity Transcription| D[GPT LLM Agent]
    D -->|Contextual Response| E{gTTS Engine}
    E -->|Audio Synthesis| F[User Audio Output]
