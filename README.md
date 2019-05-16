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

DATA - date
TIME - time
EMAIL - email
LEN - length
LOCATION - Location
ORGANIZATION - Company / Organization
PERSON - Person name
PHONE - phone number
URL - url
ZIP - ZIP code
MONEY - amount
LAW - legislation

## Hyper Parameter

max_len = 250
max_len_char = 30

character_LSTM_unit = 32
char_embedding_dim = 32
main_lstm_unit = 256 ## Bidirectional 256 + 256 = 512 ##
lstm_recurrent_dropout = 0.5

train_batch_size = 32
train_epochs = 50

## Model Architecture

__________________________________________________________________________________________________
Layer (type)                    Output Shape         Param #     Connected to                     
==================================================================================================
char_input (InputLayer)         (None, 250, 30)      0                                            
__________________________________________________________________________________________________
word_input_ (InputLayer)        (None, 250)          0                                            
__________________________________________________________________________________________________
time_distributed_1 (TimeDistrib (None, 250, 30, 32)  12768       char_input[0][0]                 
__________________________________________________________________________________________________
word_embedding (Embedding)      (None, 250, 400)     22270800    word_input_[0][0]                
__________________________________________________________________________________________________
time_distributed_2 (TimeDistrib (None, 250, 64)      16640       time_distributed_1[0][0]         
__________________________________________________________________________________________________
concatenate_1 (Concatenate)     (None, 250, 464)     0           word_embedding[0][0]             
                                                                 time_distributed_2[0][0]         
__________________________________________________________________________________________________
spatial_dropout1d_1 (SpatialDro (None, 250, 464)     0           concatenate_1[0][0]              
__________________________________________________________________________________________________
bidirectional_2 (Bidirectional) (None, 250, 512)     1476608     spatial_dropout1d_1[0][0]        
__________________________________________________________________________________________________
time_distributed_3 (TimeDistrib (None, 250, 50)      25650       bidirectional_2[0][0]            
__________________________________________________________________________________________________
crf_1 (CRF)                     (None, 250, 27)      2160        time_distributed_3[0][0]         
==================================================================================================
Total params: 23,804,626
Trainable params: 1,533,826
Non-trainable params: 22,270,800
__________________________________________________________________________________________________


## Result

* in progress *
