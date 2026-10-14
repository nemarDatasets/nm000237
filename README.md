[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000237-blue)](https://doi.org/10.82901/nemar.nm000237)

# 7-day motor imagery BCI EEG dataset from Zhou et al 2021

7-day motor imagery BCI EEG dataset from Zhou et al 2021.

## Revision note (version 1.1.0, 2026-10-14)

The BIDS recordings were regenerated with the corrected MOABB `Zhou2020` loader ([NeuroTechX/moabb#1269](https://github.com/NeuroTechX/moabb/pull/1269), issue [#1120](https://github.com/NeuroTechX/moabb/issues/1120)). Up to version 1.0.3, the recordings of subjects 1-12 (41-electrode cap) had channels named `EEG1`..`EEG41` holding the first 41 of the 45 data columns: hEOG, vEOG and the M1/M2 mastoids were stored as EEG27-EEG30 and POz, PO4, Oz and F6 were missing. They now have the 41 EEG channels with their real names and electrode positions, hEOG/vEOG as EOG and M1/M2 as MISC channels. Subjects 13-20 (26 electrodes) gain their hEOG/vEOG channels. Sampling rate, EEG values and events are unchanged. `sourcedata/` (the original files) is unchanged. See CHANGES.

## Dataset Overview

- **Code**: Zhou2020
- **Paradigm**: imagery
- **DOI**: 10.3389/fnhum.2021.701091
- **Subjects**: 20
- **Sessions per subject**: 7
- **Events**: left_hand=1, right_hand=2, feet=3, rest=4
- **Trial interval**: [0, 5] s
- **Runs per session**: 6
- **File format**: NPZ
- **Data preprocessed**: True

## Acquisition

- **Sampling rate**: 500.0 Hz
- **Number of channels**: 43
- **Channel types**: eeg=41, eog=2
- **Channel names**: F3, F1, Fz, F2, F4, FC5, FC3, FC1, FCz, FC2, FC4, FC6, C5, C3, C1, Cz, C2, C4, C6, CP5, CP3, CP1, CPz, CP2, CP4, CP6, F5, AF3, AF4, P5, P3, P1, Pz, P2, P4, P6, PO3, POz, PO4, Oz, F6
- **Montage**: standard_1005
- **Hardware**: Neuroscan SynAmps2
- **Reference**: vertex (Cz)
- **Ground**: AFz
- **Sensor type**: Ag/AgCl
- **Line frequency**: 50.0 Hz
- **Online filters**: {'bandpass': [0.5, 100], 'notch_hz': 50}

## Participants

- **Number of subjects**: 20
- **Health status**: healthy
- **Age**: mean=23.2, std=1.47, min=21, max=27
- **Gender distribution**: female=9, male=11
- **Handedness**: right-handed
- **BCI experience**: mixed
- **Species**: human

## Experimental Protocol

- **Paradigm**: imagery
- **Number of classes**: 4
- **Class labels**: left_hand, right_hand, feet, rest
- **Trial duration**: 5.0 s
- **Study design**: 7-day longitudinal MI-BCI study without feedback training. 4 classes: left hand, right hand, both feet, idle
- **Feedback type**: none
- **Stimulus type**: arrow cues
- **Stimulus modalities**: visual
- **Primary modality**: visual
- **Synchronicity**: synchronous
- **Mode**: offline

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```

  left_hand
    ├─ Sensory-event, Experimental-stimulus, Visual-presentation
    └─ Agent-action
       └─ Imagine
          ├─ Move
          └─ Left, Hand

  right_hand
    ├─ Sensory-event, Experimental-stimulus, Visual-presentation
    └─ Agent-action
       └─ Imagine
          ├─ Move
          └─ Right, Hand

  feet
    ├─ Sensory-event, Experimental-stimulus, Visual-presentation
    └─ Agent-action
       └─ Imagine, Move, Foot

  rest
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Rest

```

## Paradigm-Specific Parameters

- **Detected paradigm**: motor_imagery
- **Imagery tasks**: left_hand, right_hand, feet, rest
- **Imagery duration**: 5.0 s

## Data Structure

- **Trials**: 33600
- **Trials context**: 20 subjects x 7 sessions x 6 runs x 40 trials = 33600

## Signal Processing

- **Classifiers**: SVM
- **Feature extraction**: CSP
- **Frequency bands**: classification=[8.0, 30.0] Hz
- **Spatial filters**: CSP

## Cross-Validation

- **Method**: 10-fold
- **Folds**: 10
- **Evaluation type**: within_session

## BCI Application

- **Applications**: research
- **Environment**: laboratory
- **Online feedback**: False

## Tags

- **Pathology**: Healthy
- **Modality**: Motor
- **Type**: Research

## Documentation

- **DOI**: 10.3389/fnhum.2021.701091
- **License**: CC-BY-4.0
- **Investigators**: Qing Zhou, Jiafan Lin, Lin Yao, Yueming Wang, Yan Han, Kedi Xu
- **Institution**: Zhejiang University
- **Country**: CN
- **Repository**: Zenodo
- **Data URL**: https://zenodo.org/records/18988317
- **Publication year**: 2021

## References

Zhou, Q., Lin, J., Yao, L., Wang, Y., Han, Y., Xu, K. (2021). Relative Power Correlates With the Decoding Performance of Motor Imagery Both Across Time and Subjects. Frontiers in Human Neuroscience, 15, 701091. https://doi.org/10.3389/fnhum.2021.701091

Zhou, Q. et al. (2020). EEG dataset of 7-day Motor Imagery BCI. IEEE DataPort. https://doi.org/10.21227/f1c7-7x89
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.8.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
