https://github.com/openai/whisper

Requirements:
- Python 3.8+
- `whisper` - `pip install -U openai-whisper`
- ffmpeg (https://www.gyan.dev/ffmpeg/builds/)

```python
# outputs srt file
# uses snippet from: https://github.com/openai/whisper/discussions/98

import whisper

model = whisper.load_model("turbo")
result = model.transcribe("source.mp3")

segments = result["segments"]

with open("output.srt", "a", encoding="utf-8") as out:
    for segment in segments:
        start_time = str(0) + str(timedelta(seconds=int(segment["start"]))) + ",000"
        end_time = str(0) + str(timedelta(seconds=int(segment["end"]))) + ",000"
        text = segment["text"]
        segment_id = segment["id"] + 1
        segment = f"{segment_id}\n{start_time} --> {end_time}\n{text[1:] if text[0] == ' ' else text}\n\n"
        out.write(segment)
```