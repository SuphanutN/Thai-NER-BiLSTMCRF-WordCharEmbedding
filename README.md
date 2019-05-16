# Thai-NER-BiLSTM-CRF-WordCharEmbedding
Thai Named Entity Recognition with BiLSTM-CRF using Word/Character Embedding

Author: Suphanut Thattinaphanich

* The paper will release soon in some conference in the future (still in progress) *

## Description

The Thai Named Entity Recognition model use Bi-directional LSTM with Word / Character representation and CRF for sequece tagging
Perform keras backend

- Word Embedding : v. 0.32 Thai2Fit 400 dimension
- Char Embedding : Bi-LSTM training from scratch 32 dimension

## Thank to 
- Wannaphong Phatthiyaphaibun (https://github.com/wannaphongcom/thai-ner) for the initial of the Thai NER project
- https://www.depends-on-the-definition.com/lstm-with-char-embeddings-for-ner/ for embedding method
- Charin (https://github.com/cstorm125/thai2fit) for the word embbeding (Thai2Fit)

## Dataset

The dataset is come from (https://github.com/wannaphongcom/thai-ner/blob/master/model/1.1/datatrain.data)

Tag

- DATA - date
- TIME - time
- EMAIL - email
- LEN - length
- LOCATION - Location
- ORGANIZATION - Company / Organization
- PERSON - Person name
- PHONE - phone number
- URL - url
- ZIP - ZIP code
- MONEY - amount
- LAW - legislation

## Hyper Parameter

- max_len = 250
- max_len_char = 30
- character_LSTM_unit = 32
- char_embedding_dim = 32
- main_lstm_unit = 256 ## Bidirectional 256 + 256 = 512 ##
- lstm_recurrent_dropout = 0.5
- train_batch_size = 32
- train_epochs = 50

## Result

* in progress *
