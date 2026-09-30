# Sahayak
Many students in India study with unreliable internet, limited data plans and shared devices. Cloud AI tools need a connection, send personal notes to a server, and mostly work best in English. A student recording a lecture in Hindi or Kannada mixed with English has almost no good offline option.

**An offline AI study companion for Snapdragon-powered HP PCs.**
Turns lectures, handwritten notes and PDFs into summaries and flashcards, on the laptop's NPU, with no internet and no data leaving the device.

> Status: ** 

## Why I built this
Multilingual support for Indian languages with code-mixed speech, which most offline tools ignore.

## What it does
1. **Listen**: transcribes lectures in English, Hindi and Kannada (Whisper)
2. **Read**: extracts text from photos of notes and whiteboards (OCR)
3. **Understand**: answers questions about your own material (embeddings + small on-device LLM)
4. **Revise**: summaries, flashcards and a "revision tonight" mode

## Snapdragon / NPU optimisation
- Native Windows on ARM64 (no x64 emulation)
- Models from Qualcomm AI Hub / open source, run through ONNX Runtime with the QNN execution provider (HTP backend)
- CPU fallback only where a model is unsupported
- Built-in benchmark comparing NPU and CPU

## Tested on
- Device: **[HP model]**
- Chip: **[Snapdragon X ...]**
- OS: **[Windows 11 ARM64, version]**

## Quick start
```
git clone https://github.com/Suchith/sahayak.git
cd sahayak
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python check_npu.py
```
`check_npu.py` should list `QNNExecutionProvider`. If it doesn't, the NPU path is not active.

## License
MIT. See LICENSE.
