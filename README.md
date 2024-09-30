```markdown
# Text-to-Speech (TTS) with XTTS v2

This repository demonstrates how to use the XTTS v2 model from the TTS package for multilingual text-to-speech synthesis.

## Setup

**1. Install Python:**

Download and install a compatible version of Python from the official website:

[https://www.python.org/ftp/python/3.10.8/python-3.10.8-amd64.exe](https://www.python.org/ftp/python/3.10.8/python-3.10.8-amd64.exe)

**2. Create Virtual Environment:**

Create a new virtual environment to manage dependencies:

```bash
py -3.10 -m venv tts_env
```

**3. Activate Virtual Environment:**

Activate the virtual environment:

```bash
tts_env\Scripts\activate 
```

**4. Install TTS Package:**

Install the TTS package within the virtual environment:

```bash
pip install TTS
```

## Inference

**1. Create Project Folder:**

Create a new folder named "TTS":

```bash
mkdir TTS
```

**2. Navigate to Folder:**

Change to the newly created directory:

```bash
cd TTS
```

**3. Create Inference Script:**

Create a file named `inference.py` and paste the following code:

```python
import torch
from TTS.api import TTS

device = "cuda" if torch.cuda.is_available() else "cpu"

tts = TTS("tts_models/multilingual/multi-dataset/xtts_v2").to(device)
tts.tts_to_file(text="Hello world!", speaker_wav="my/cloning/audio.wav", language="en", file_path="output.wav") 
```

**4. Run Inference:**

Execute the `inference.py` script:

```bash
python inference.py
```

This will generate an audio file named `output.wav` containing the synthesized speech.

**Note:** 

- Replace `"my/cloning/audio.wav"` with the path to your speaker's audio file for voice cloning.
- You can modify the `text` and `language` parameters to generate speech in different languages.


## Acknowledgments

- This project utilizes the [TTS](https://github.com/coqui-ai/TTS) package.
```
