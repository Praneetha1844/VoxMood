# Data

The audio is **not included**. Download RAVDESS from https://zenodo.org/record/1188976 (the Ryerson Audio-Visual Database of Emotional Speech and Song) and place the `Actor_01` to `Actor_24` folders inside `data/ravdess/`:

```
data/ravdess/
  Actor_01/03-01-01-01-01-01-01.wav
  Actor_02/...
```

## File names

Each file name has seven numeric fields: `modality-vocal channel-emotion-intensity-statement-repetition-actor.wav`.

| Field | Used for |
|---|---|
| 3rd (emotion) | the label: 01 neutral, 02 calm, 03 happy, 04 sad, 05 angry, 06 fearful, 07 disgust, 08 surprised |
| 7th (actor) | the speaker id, used for the speaker-independent check |

The notebook keeps calm, happy, fearful and disgust. According to the RAVDESS documentation, the speech-only release has 192 recordings for each of those emotions (768 files in total). These numbers come from the dataset documentation and were not counted in this repository. Check them against your download.

## Licence

RAVDESS is published on Zenodo under a Creative Commons licence that restricts commercial use. Check the Zenodo record for the current terms before reuse or redistribution. Do not commit the audio files. They are large and are not part of this repository.
