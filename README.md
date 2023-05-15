# MVSEP-MDX23-music-separation-model
Model for [Sound demixing challenge 2023: Music Demixing Track - MDX'23](https://www.aicrowd.com/challenges/sound-demixing-challenge-2023). Model perform separation of music into 4 stems "bass", "drums", "vocals", "other". Model won 3rd place in challenge (Leaderboard C).

Model based on [Demucs4](https://github.com/facebookresearch/demucs), [MDX](https://github.com/kuielab/mdx-net) neural net architectures and some MDX weights from [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui) project (thanks [Kimberley Jensen](https://github.com/KimberleyJensen) for great high quality vocal models). Brought to you by [MVSep.com](https://mvsep.com).
## Usage

```
    python inference.py --input_audio mixture1.wav mixture2.wav --output_folder ./results/
```

With this command audios with names "mixture1.wav" and "mixture2.wav" will be processed and results will be stored in `./results/` folder in WAV format.

**Note**: By default inference requires at least 11 GB of video memory. If you have less memory you can use CPU (`--cpu`) or use single ONNX (`--single_onnx`). Also reduce of chunk size can help (`--chunk_size 200000`).

**Colab Notebook**: <a href="https://colab.research.google.com/github/justinjohn0306/MVSEP-MDX23-music-separation-model/blob/main/MVSEP_MDX23_music_separation_model.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Quality comparison

Quality comparison with best separation models performed on [MultiSong Dataset](https://mvsep.com/quality_checker/leaderboard2.php?sort=bass). 

| Algorithm     | SDR bass  | SDR drums  | SDR other  | SDR vocals  | SDR instrumental  |
| ------------- |:---------:|:----------:|:----------:|:----------:|:------------------:|
| MVSEP MDX23   | 12.5034   | 11.6870    | 6.5378     |  9.5138    | 15.8213            |
| Demucs HT 4   | 12.1006   | 11.3037    | 5.7728     |  8.3555    | 13.9902            |
| Demucs 3      | 10.6947   | 10.2744    | 5.3580     |  8.1335    | 14.4409            |
| MDX B         | ---       | ----       | ---        |  8.5118    | 14.8192            |

* Note: SDR - signal to distortion ratio. Larger is better.

## GUI

![GUI Window](https://github.com/ZFTurbo/MVSEP-MDX23-music-separation-model/blob/main/images/MVSep-Window.png)

* Script for GUI (based on PyQt5): [gui.py](gui.py).
* You can download standalone program for Windows here: [zip1](https://github.com/ZFTurbo/MVSEP-MDX23-music-separation-model/releases/download/v1.0/MVSep-MDX23.zip.001), [zip2](https://github.com/ZFTurbo/MVSEP-MDX23-music-separation-model/releases/download/v1.0/MVSep-MDX23.zip.002). Unzip archives and to start program double click `run.bat`.
* At first run program will download all needed neural net models from internet.
* GUI supports Drag & Drop of multiple files.
* Progress bar available.

## Citation

TBD
