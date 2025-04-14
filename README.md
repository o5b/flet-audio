# Flet Audio control

`Audio` control for Flet. This fork includes the Flutter plugin [wakelock_plus](https://github.com/fluttercommunity/wakelock_plus), which allows keeping the device screen active, preventing it from going into sleep mode.

## Usage

Add `flet-audio` as dependency (`pyproject.toml` or `requirements.txt`) to your Flet project.

```
flet-audio @ git+https://github.com/o5b/flet-audio.git
```

### Add `flet-audio` as dependency `pyproject.toml`. Example:

```
dependencies = [
  "flet-audio @ git+https://github.com/o5b/flet-audio.git",
  "flet>=0.26.0",
]
```

### Add `flet-audio` as dependency `requirements.txt`. Example:

```
flet[all]==0.26.0
flet-audio @ git+https://github.com/o5b/flet-audio.git
```

## Example

```py

import flet as ft

import flet_audio as fta


def main(page: ft.Page):
    audio1 = fta.Audio(
        src="https://luan.xyz/files/audio/ambient_c_motion.mp3", autoplay=True
    )
    page.overlay.append(audio1)
    page.add(
        ft.Text("This is an app with background audio."),
        ft.ElevatedButton("Stop playing", on_click=lambda _: audio1.pause()),
    )

ft.app(main)
```