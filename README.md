# Speech to Text

A small Python script that listens to a selected microphone, waits for the Korean wake word `안녕`, and converts the next spoken sentence to text.

## Features

- Lists available audio input devices
- Allows microphone selection
- Calibrates for ambient noise
- Detects the wake word `안녕`
- Recognizes Korean speech using Google Speech Recognition

## Requirements

- Python 3
- A working microphone and microphone permissions
- Internet access
- `SpeechRecognition`
- `PyAudio`

```bash
pip install SpeechRecognition PyAudio
```

`PyAudio` may require additional system audio libraries depending on your operating system.

## Usage

```bash
python speech_to_text.py
```

The program lists audio devices, asks for a device number, waits for `안녕`, then listens for one more sentence and prints the recognized text. It exits after successful recognition.

## Notes

- Speech recognition is configured for Korean (`ko-KR`).
- Recognition uses Google's speech-recognition service through `SpeechRecognition`, so an internet connection is required.
- Unrecognized audio is ignored and listening continues.
- The wake word is hard-coded as `안녕` in `speech_to_text.py`.
- Press `Ctrl+C` to stop the program.

No license has been specified for this repository.
