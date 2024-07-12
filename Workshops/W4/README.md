## Visual Question Answering (VQA)
In this notebook, I used mscoco dataset.  
Main steps are:
- Preparing dataset: For this porpuse, we converted the task of VQA to a classification task. Most frequent answers were collected to be our classes. This is done
  because we don't have powerful resources and training on all kind of answers is really costly.
- Building model: For this porpurse, I have used an image encoder and a text encoder, then feeding the concatenated version of them through a feed-forward network
  to predict the final answer. ResNet18 is used as image encoder and Bert is used as text encoder.
