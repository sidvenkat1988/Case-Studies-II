# Case-Studies-II
This is done as a part of my university module in which I aim to recognize faces and voices using Autoencoders. The datasets chosen were:
1) Labelled Faces in the Wild for face classification and
2) LibriSpeech ASR corpus for voice classification.

The pre-processing steps were:
1) For the faces dataset:
1.1) Data Augmentation
1.2) Face detection with key-points marked on the eyes, nose and mouth
1.3) Cropping the faces from the augmented image
1.4) Retaining only the authentic faces based on the labels tagged against them in the raw dataset(in cases of multiple faces being detected and cropped per image)

2) For the voices dataset:
2.1) For the Mel-spectrigrams:
2.1.1) Break the audio samples into 1 second chunks
2.1.2) Extract the Mel-spectrograms for each 1 second chunk
2.1.3) Visualize and store them as images
2.2) For the MFCCs
2.2.1) Extract 40 MFCCs per audio sample irrespective of their length

The final corpora comprised of:
1) 40000 single-faced images with 250 images per head for 160 distinct individuals
2) 40000 Mel-Spectrogram images – each representing 1 second audio clippings. Sampled at 250 clippings per head for 160 distinct speakers
3) 10000 MFCC features with 100 features per head for 100 distinct speakers


Two types of Autoencoder techniques were implemented:
1) Convolutional Autoencoder - To learn the latent features of the faces and Mel-spectrograms
2) Deep Autoencoders - To learn the latent features of MFCCs

The pre-trained weights of the Autoencoders were used for the encoder network with additional dense layers to classify faces and voices. 

1) The convolutional encoder with it's corresponding pre-trained autocoder weights attained a validation accuracy of 82.975% on the faces data
2) The convolutional encoder with it's corresponding pre-trained autocoder weights attained 0% validation accuracy on the Mel-spectrograms extracted from the voices data
2) The deep encoder with it's corresponding pre-trained autocoder weights attained a test accuracy of 95% on the MFCCs extracted from the voices data. 



The models folder contains the notebooks in which the face and the voice models were trained.

The Face Data Preprocessing and the Voice Data Preprocessing folders contain the notebooks in which all the preprocessing steps were followed.

All the raw data, transformed data and the steps followed in the implementation of this project can be found in this link:
https://drive.google.com/drive/folders/1N6r4pdfmhDq6p874g8XmA1bJMAD-vRi_?usp=sharing

Run the Demo.ipynb in order to test the model's accuracy on the demo dataset available in the link below:
https://drive.google.com/open?id=1B4k2eDfIrHeRAlbC9ItF_8NMgsqqThJs

The pre-trained models with their weights have been saved in the link below:
https://drive.google.com/open?id=1BCYWD8OZFTkvI5LX4iXuyU00w5815raM
