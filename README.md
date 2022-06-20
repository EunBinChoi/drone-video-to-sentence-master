# Drone-Video-to-Sentence (DV2S)

## Problem
Real-world drone videos often have complex dynamics; and methods for generating open-domain video descriptions should be sensitive to temporal structure and allow both input (sequence of frames) and output (sequence of words) of variable length. In addtion, global motion exists in drone videos because the drone videos are captured by camera attached to the drone while the drone is flying.

## Solution
To approach this problem, we propose a novel end-to-end sequence-to-sequence model to generate captions for drone videos. For this we exploit recurrent neural networks, specifically LSTMs, which have demonstrated stateof-the-art performance in image caption generation. Our LSTM model is trained on video-sentence pairs and learns to associate a sequence of drone video frames to a sequence of words in order to generate a description of the event in the drone video clip. Our model naturally is able to learn the temporal structure of the sequence of frames as well as the sequence model of the generated sentences, i.e. a language model. We evaluate several variants of our model that exploit different visual features on a standard set of YouTube drone videos. The main contribution of this work is to propose a novel model, S2VT, which learns to directly map a sequence of frames to a sequence of words. A stacked LSTM first encodes the frames one by one, taking as input the output of a Convolutional Neural Network (CNN) applied to each input frame’s intensity values. Once all frames are read, the model generates a sentence word by word. The encoding and decoding of the frame and word representations are learned jointly from a parallel corpus. To model the temporal aspects of activities typically shown in videos, we also compute the optical flow between pairs of consecutive frames. The flow images are also passed through a CNN and provided as input to the LSTM. Flow CNN models have been shown to be beneficial for activity recognition.

## Tools && Lagnguage
- Deep lean


Reference
If you find this code helpful, please consider citing:

[Sequence to Sequence - Video to Text] [https://vsubhashini.github.io/s2vt.html]

S. Venugopalan, M. Rohrbach, J. Donahue, T. Darrell, R. Mooney, K. Saenko
The IEEE International Conference on Computer Vision (ICCV) 2015
