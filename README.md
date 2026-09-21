# TTS Model

A desktop text-to-speech studio built with Python, Tkinter, and Kokoro. Write text, choose from regional voice profiles, play the generated speech, or save it as a WAV file.

## Features

- American, British, and Indian English voice profiles
- 24 selectable voice styles
- Background model loading so the window opens immediately
- Audio playback through `sounddevice`
- WAV export without requiring FFmpeg
- Windows executable build configuration included
- Explicit packaging for Kokoro, eSpeak NG, and language registry data

## Requirements

- Windows 10 or newer
- Python 3.12 recommended
- A working audio output device
- Internet access on first run so Kokoro can download its model from Hugging Face

The model is downloaded and cached by Kokoro on first use. The first generation can take longer than later generations.

## Setup

Create and activate a virtual environment, then install the dependencies used by the application:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install kokoro sounddevice numpy pydub pyinstaller
```

Run the application from source:

```powershell
python tts.py
```

## Build the Windows Application

The included `tts.spec` builds a windowed, onedir executable and includes the runtime data required by Kokoro and eSpeak NG:

```powershell
.\.venv\Scripts\python.exe -m PyInstaller --noconfirm --clean tts.spec
```

The executable is created at:

```text
dist\tts\tts.exe
```

Distribute the complete `dist\tts` folder, including its `_internal` directory. Do not copy only the executable.

## Usage

1. Start the application.
2. Enter or edit the text.
3. Select a voice profile.
4. Click **Play Voice Output** to listen.
5. Click **Download Voice Output** to save a WAV file.

## Project Files

- `tts.py` - application source
- `tts.spec` - PyInstaller build configuration
- `dist/tts/` - generated Windows application bundle

## License

This project is provided for personal and educational use. Review the licenses of Kokoro, PyTorch, eSpeak NG, and all other dependencies before redistributing the application.

### Download 🚀

You can download the the main zip from the releases area by downloading the zip. 

