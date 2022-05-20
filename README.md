# Speech-Emotion-Recognition

## Problem statement

Speech is the most natural way of expressing ourselves as humans. It is only natural 
then to extend this communication medium to computer applications. We define 
speech emotion recognition (SER) systems as a collection of methodologies that 
process and classify speech signals to detect the embedded emotions.<br>
The data come from Kaggle. I've used the CREMA data set which can be found [here](https://link-url-here.org).<br>
We should diffrentiate six classes which are {happy,sad,angry,disgust,neutral,fear}

## Pre-processing and splitting the data

I've used **torchaudio** and **librosa** libraries to extract audio features.<br>
First the audio was loaded to get the wavefrom and the power spectrum as following:
![alt text]([http://url/to/img.png](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/waveform.png))
![alt text]([http://url/to/img.png](https://github.com/AmrMomtaz/Speech-Emotion-Recognition/blob/main/Images/power_spectrum.png))
torchaudio was used for extracting 2D audio features (Mell spectrogram) with 64 coefficients. 
