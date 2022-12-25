# Open-Set Speech Language Identification and the CU MultiLang Dataset

#### Mustafa Eyceoz, Justin Lee, Siddarth Pittie

## Publication

TITLE PENDING
 - URL PENDING

## Previous Works

Modernizing Open-Set Speech Language Identification
 - Our original paper that inspired this continued work
 - [arXiv Publication URL](https://arxiv.org/abs/2205.10397)
 - [Git Repo](https://github.com/jjlee0802cu/open-set-lid)

## Project Summary
Building an accessible, robust, and general solution for open-set speech language identification.
Also building a diverse, high-coverage, open-source speech dataset spanning over 50 languages.

## CU MultiLang Dataset
The full dataset can be accessed at the below link:
 - [Link to Dataset](https://console.cloud.google.com/storage/browser/cu-multilang-dataset)

## LID System Code Guide

**Run demo**

```
$ python3 full_system.py
```

**Train TDNN with 5hrs, 4sec, 15 epochs**

```
$ python3 train_tdnn.py 5 4 15 0.8
```

**Test the tdnn-final-submission TDNN model**

```
$ python3 test_tdnn.py ./saved-models/tdnn-final-submission.pickle
```

**Save the outputs of tdnn-final-submission TDNN model**

```
$ python3 get_tdnn_outputs.py ./saved-models/tdnn-final-submission.pickle
```

**Train LDA and pLDA layers using saved-tdnn-outputs**

```
$ python3 train_lda_plda.py ./saved-tdnn-outputs
```

## Feature Generation
MFCC + pitch features were generated using Kaldi
 - MFCC and pitch conf files can be found in the `mfcc-confs` subdir
   - Originally found in `kaldi/egs/tedlium/s5_r3/scripts/conf/mfcc.conf` and `kaldi/egs/tedlium/s5_r3/scripts/conf/pitch.conf`
 - Also in that subdir is our modified version of the `make_mfcc_pitch.sh` script
   - Originally found in and runnable from

## Open-Source Citations
Language Data Sources
 - [MediaSpeech](https://openslr.org/108/)
 - [African Accented French](https://openslr.org/57/)
 - [Crowdsourced high-quality Chilean Spanish speech data set](https://www.openslr.org/71/)
 - [Crowdsourced high-quality Colombian Spanish speech data set](https://www.openslr.org/72/)
 - [Crowdsourced high-quality Peruvian Spanish speech data set](https://www.openslr.org/73/)
 - [Crowdsourced high-quality Puerto Rico Spanish speech data set](https://www.openslr.org/74/)
 - [Free ST American English Corpus](https://openslr.org/45/)
 - [FHNW Swiss Parliament](https://huggingface.co/datasets/Yves/fhnw_swiss_parliament)
 - [Samromur 21.05](https://www.openslr.org/112/)
 - [VoxForge](http://www.voxforge.org/home)
 - [Russian LibriSpeech](https://openslr.org/96/)
 - [BibleTTS](https://openslr.org/129/)
 - [Iban](https://www.openslr.org/24/)
 - [Crowdsourced high-quality Burmese speech data set](https://openslr.org/80/)
 - [VoxLingua107](http://bark.phon.ioc.ee/voxlingua107/)
 - [Crowdsourced high-quality Telugu multi-speaker speech data set](https://openslr.org/66/)

Basic PyTorch TDNN Reference
 - https://github.com/cvqluu/TDNN

Python pLDA Reference:
- https://github.com/RaviSoji/plda
