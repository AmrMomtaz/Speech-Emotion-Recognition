# Speech-Emotion-Recognition

## Problem statement

Speech is the most natural way of expressing ourselves as humans. It is only natural 
then to extend this communication medium to computer applications. We define 
speech emotion recognition (SER) systems as a collection of methodologies that 
process and classify speech signals to detect the embedded emotions.<br>
The data come from Kaggle. I've used the CREMA data set which can be found [here](https://link-url-here.org).<br>
We should diffrentiate six classes which are {happy,sad,angry,disgust,neutral,fear}.<br>
Here is the audio durations distrbution and the classes distrubution:<br>
![alt text](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/audio_durations.png)
![alt text](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/audio_dist.png)<br><br>
The classes are balanced so we won't need to over-sample or under-sample the data.

## Pre-processing and splitting the data

I've used **torchaudio** and **librosa** libraries to extract audio features.<br>
First the audio was loaded to get the wavefrom and the power spectrum as following:
![alt text](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/waveform.png)
![alt text](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/power_spectrum.png)<br>
In the audio pre-processing pipeline the following steps were taken:
* All audio were resampled to have a fixed sample rate.
* All audio are padded and cutted to have 4 secs length.
* All audio were mixed down to 1 single channel.<br>


Then torchaudio was used for extracting 2D audio features (Mell spectrogram) with 64 coefficients. Or librosa was used to extract 1D features like zero-crossing-rate.
Then the data wwas splitted 70% for training and validation (5% for validation) and 30% for testing (stratifying was applied)
