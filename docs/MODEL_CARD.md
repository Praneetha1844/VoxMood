# Model card: VoxMood

## Summary

A scikit-learn multilayer perceptron that classifies the emotion of an acted speech recording as one of four classes (calm, happy, fearful, disgust), using averaged MFCC, chroma and mel-spectrogram features. It is a learning project adapted from a public tutorial, not a production system.

## Intended use

- Studying a classic audio-features plus MLP pipeline.
- A baseline for comparing other models on RAVDESS.

**Not intended for:** inferring the emotions of real people, hiring, call-centre monitoring, mental-health use or any decision that affects someone.

## Data

RAVDESS: acted speech from 24 professional actors in a North American accent, recorded in a studio. Audio is not included. See [data/README.md](../data/README.md).

## Model

- Features per file: the mean over time of 40 MFCCs, the chroma STFT and the mel spectrogram, concatenated.
- Classifier: `MLPClassifier(hidden_layer_sizes=(300,), alpha=0.01, batch_size=256, learning_rate='adaptive', max_iter=500, random_state=9)`.
- Split: random by file, `test_size=0.25`, `random_state=9`.

## Results

The saved notebook has no outputs, so **no accuracy figure is reported**. Per-class and speaker-independent cells are included but have not been run.

## Limitations and risks

- **Speaker leakage in the default split.** The same actor can appear in train and test, which can inflate accuracy. A speaker-independent cell is provided for a fairer estimate.
- **Acted, studio-quality speech.** Real spontaneous speech, noise, other languages and other accents are untested.
- **Four of eight emotions only.** Results do not apply to the full label set.
- **Subjective labels.** Emotion categories are culturally dependent, and an actor's portrayal is not the same as an inner state.
- **Demographic bias.** Only 24 actors; performance across genders, ages and accents is unknown.
- **No feature scaling, cross-validation or tuning.**
- **Misuse risk.** Inferring emotion from voice can be inaccurate and can discriminate. Do not use it to judge people.

## Provenance

The feature extraction and model set-up are adapted from the DataFlair speech emotion recognition tutorial, which is credited in the notebook and the README. The tutorial's own licence terms are not stated here. The MIT licence of this repository covers the modifications and additions made in it.
