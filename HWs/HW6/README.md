## Implementing and Training a Masked Language Model (MLM)
We used bookcorpus dataset to train the MLM on.  
Main steps are:
- Data preparation: This stage is mainly about Masking Strategy. We follow the one used in pretraining Bert model. 15 percents of tokens are selected,
  80 percents of them are masked, 10 percents replaced with random word, and 10 percents left unchanged.
- Model Definition: The model is a Transformer-Based one. Each Transformer Block consists of a Multi-Head Self-Attention, a feed-forward layer, two dropout
  and skip connections. Each Encoder aggregates multiple Transformer Blocks to process the input text. Finally the MLM consists of multiple Encoders.
- Training Model
- Evaluating Model
