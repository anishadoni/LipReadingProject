# LipReadingProject
An automated lip reading algorithm that leverages a combination of convolutional neural networks (CNNs) and LSTMs in order to read lips based purely on visems. 

# Data Collection
One of my project teamamtes recorded videos of him vocalizing English phonemes in at uniform frequences at equally spaced intervals. E.g. the phoneme "ah" would have been enunciated roughly 100 times, 1 second apart, to obtain an empirical distribution of the phoneme. The videos were recorded by a camcorder at 30fps and then split into individual frames.

# Data Preprocessing
In the first iteration of the project, the data was split into individual frames, and the individual frames were passed as raw input into our model. To speed up training and eliminate potential erroneous data, we included a facial segmentation algorithm in the data preprocessing pipeline which would isolate only the lip movements to be used as input for our model. With our limited compute resources, lip segmentation provided decent performance, but full facial expressions would most likely enhance model performance by providing additional, potentially helpful signals for the model to interpret certain phonemes.

# Model Development and Training
We chose to use a CNN-LSTM model. The CNN is the state-of-the-art computer vision and deep learning algorithm for image interpretation and analysis, and it functinoed as an encoder in our model, transforming each image into a latent space. Finally, the LSTM served to decode the encoded images while incorporating the time-based nature of lip movements to successfully determine the phonetic sounds corresponding to each phoneme.
