#**Wake Word Detection using CNN**

**Dataset**

This project uses the Google Speech Commands Dataset, sourced from Kaggle:
https://www.kaggle.com/datasets/neehakurelli/google-speech-commands

The target wake word selected for training was “Marvin.”

To improve model robustness and increase the number of negative samples, additional environmental noise clips were incorporated from the following dataset:
https://www.kaggle.com/datasets/javohirtoshqorgonov/noise-audio-data

Augmenting the dataset with diverse background noise helps improve generalization and reduces false positives in real-world deployment scenarios.

**Feature Extraction**

Mel-Frequency Cepstral Coefficients (MFCCs) were used as the primary feature representation. MFCCs are well-suited for speech recognition tasks because:

They operate on the mel scale, which approximates human auditory perception.

They apply logarithmic compression, capturing perceptually relevant frequency information.

They produce a compact representation compared to full spectrograms, reducing computational complexity.

To build foundational understanding of audio signal processing concepts, the following educational resources were referenced:

Audio Signal Processing Playlist:
https://youtu.be/iCwMQJnKk2c?si=9HG2GvISXJCjSV_T

Step-by-step explanation of MFCC computation:
https://www.geeksforgeeks.org/nlp/mel-frequency-cepstral-coefficients-mfcc-for-speech-recognition/

**Model Architecture**

A Convolutional Neural Network (CNN) was chosen for this task. CNNs are particularly effective for audio classification when features are represented as time-frequency maps (such as MFCCs), as they can learn spatially local and hierarchical patterns.

The decision to use a CNN instead of a fully connected neural network was based on several advantages:

Parameter sharing, which significantly reduces the number of learnable parameters compared to dense networks.

Local receptive fields, enabling the model to capture recurring time-frequency patterns in speech signals.

Improved generalization with relatively smaller datasets due to reduced model complexity.

Compatibility with model quantization for deployment on resource-constrained devices.

Pooling layers were incorporated to reduce spatial dimensions, lower computational cost, and further decrease memory requirements—particularly important for embedded or edge deployment scenarios.
