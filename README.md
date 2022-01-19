# Arabic-phoneme-recognition-few-shot-learning
This repository's codebase uses few shot learning with a siamese network to recognize/classify individual, isolated Arabic phonemes. Using a pre-trained model (TRILL) from TensorFlow Hub to generate embeddings for each phoneme example we have per letter, we then take pairs of the phonemes as inputs to the siamese network, which outputs whether or not they belong to the same letter.

The idea was that because each letter in the Arabic language has a unique phoneme, then maybe with few-shot learning (using a few examples) we could produce an effective classifier. You might be thinking why we'd want to classify individual, isolated phonemes when speech to text is meant for full words and phrases. However, this could help those that are new to the language learn how to pronounce the individual sounds and letters correctly.

### Repo Structure
- `/test_data` - folder that contains the sample phonemes used for few-shot learning (all from same speaker)
- `/letter_images` - folder that contains images corresponding to each letter in Arabic (for presentation of outputs of model)
- `Arabic_phoneme_classifier_few_shot_learning.ipynb` - Notebook with all relevant/necessary code for this project

### Improvement
There is plenty of room for improvement as the final model did not perform as well on examples outside of the provided speaker. Potential improvements include:
- Using a speech to text pre-trained model trained on Arabic-exclusive audio
- Adding a more examples from a few different speakers
- Experimenting with more audio pre-processing (especially to accommodate for inference data that will come from poor quality microphones)

### Lessons Learned
- Audio data is difficult to work with
- Don't use TensorFlow (too many nuances and very finicky)

### Resources used
- Siamese Network tutorial (for MNIST image data)
  - [Building image pairs](https://www.pyimagesearch.com/2020/11/23/building-image-pairs-for-siamese-networks-with-python/)
  - [Training Siamese Networks with Keras & TF](https://www.pyimagesearch.com/2020/11/30/siamese-networks-with-keras-tensorflow-and-deep-learning/)
  - [Comparing images using Siamese Networks](https://www.pyimagesearch.com/2020/12/07/comparing-images-for-similarity-using-siamese-networks-keras-and-tensorflow/)
  - [Contrastive Loss for Siamese Networks](https://www.pyimagesearch.com/2021/01/18/contrastive-loss-for-siamese-networks-with-keras-and-tensorflow/) (optional)
- [Helper functions for audio pre-processing on TensorFlow](https://www.tensorflow.org/tutorials/audio/transfer_learning_audio)
- [TRILL pre-trained model](https://tfhub.dev/google/nonsemantic-speech-benchmark/trill/3) (from TensorFlow Hub)
