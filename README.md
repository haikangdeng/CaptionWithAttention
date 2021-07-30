# CaptionWithAttention
Attention-based Image Caption Generator

![demo_image](https://user-images.githubusercontent.com/59696511/127633817-d4bc4b84-ce8c-4ae5-9391-de780547b7c9.png)
<br/>

This image-language model takes advantage of LSTM and pretrained ResNet and GloVe. A fancy idea is that the model extracts two features from input image using ResNet, one of size `(7, 7, 2048)` and the other of size `(2048)`. The former feature contains location information while the latter one has more concentrated information in each channel. In practice, the former feature is attended to LSTM states to generate context vector in each step, which is then concatenated with input word vector to form LSTM input. The latter feature(concentrated), after running through a linear layer, is passed to the LSTM as initial cell state.
<br/>
<br/>
**Materials:**
<br/>
`flickr8k/`: Dataset consists of 8,000 images that are each paired with five different captions. Download here: https://www.kaggle.com/adityajn105/flickr8k
<br/>
`glove.6B.200d.txt`: Pretrained word vectors based on unsupervised learning algorithm GloVe. We use 6B tokens, 200 dimension vectors in this model. Download here: https://nlp.stanford.edu/projects/glove/
<br/>
`test/`: Contains photos for testing.
<br/>
<br/>
**Attention:** (pun)
<br/>
Put `flickr8k/`, `test/`, and `glove.6B.200d.txt` under the same directory with `CaptionWithAttention.ipynb`.
<br/>
<br/>
**References:**
<br/>
*Image Captioning* by AladdinPersson, link: https://github.com/aladdinpersson/Machine-Learning-Collection/tree/master/ML/Pytorch/more_advanced/image_captioning
<br/>
*Tensorflow Turotial*, link: https://www.tensorflow.org/tutorials/text/image_captioning#caching_the_features_extracted_from_inceptionv3
