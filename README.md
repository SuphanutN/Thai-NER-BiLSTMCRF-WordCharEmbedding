# Thai-NER-BiLSTM-CRF-WordCharEmbedding
Thai Named Entity Recognition with BiLSTM-CRF using Word/Character Embedding

https://www.researchgate.net/publication/336798652_Thai_Named_Entity_Recognition_Using_Bi-LSTM-CRF_with_Word_and_Character_Representation

Medium

https://medium.com/@NagisaZ/thai-named-entity-recognition-with-bilstm-crf-using-word-character-embedding-keras-6834717d4fdb

## Description

The Thai Named Entity Recognition model use Bi-directional LSTM with Word / Character representation and CRF for sequece tagging
Perform keras backend

- Word Embedding : v. 0.32 Thai2Fit 400 dimension
- Char Embedding : Bi-LSTM training from scratch 32 dimension

# Requirements

* python = 3.5.2 +
* keras = 2.1.6 +

## Dataset

The dataset retrieve from (https://github.com/wannaphongcom/thai-ner/blob/master/model/1.1/datatrain.data)

This dataset is ThaiNER crowdsourcing project. 
If someone interest to contribute this project, you can help labelling the dataset at https://thainlp-203815.appspot.com/add.html?fbclid=IwAR0EnfMJQyVE2z1md66hDjreR8m1y2kt99b_TbqbssMrazwnMq4SQHt9w4I

The dataset contain 6,148 sentences (197,704 words / 50,593 NER tokens) in BIO format. 

Split random sentences as train 80% test 20%. 

Train: 4,918 sentences (157,467 words / 40,545 NER tokens‬)

Test: 1,230 sentences (40237 words / 10,048 NER tokens)

Tag

- DATE - date
- TIME - time
- EMAIL - email
- LEN - length
- LOCATION - location
- ORGANIZATION - company / organization
- PERSON - person name
- PERCENT - percent number
- PHONE - phone number
- URL - url
- ZIP - ZIP code
- MONEY - amount of money
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

## Model

The model is too large, you can train it yourself with the given dataset or the update dataset.

Or you can download my model weight at this link below and save in your model path (For me, MODEL_PATH = f'{DATA_PATH}model/Keras/WordCharModel/')

- https://drive.google.com/open?id=1RIeAgJVqWRVvDjlCOBetTYHmyea9XYg5

the result shown below use ep.46 from 50 epoch


## Result
```
                precision    recall  f1-score   support

        B-DATE     0.9558    0.9177    0.9364       401
       B-EMAIL     1.0000    1.0000    1.0000         1
         B-LAW     0.6667    0.7200    0.6923        25
         B-LEN     0.8077    0.9545    0.8750        22
    B-LOCATION     0.8891    0.8971    0.8931       894
       B-MONEY     0.9771    0.9624    0.9697       133
B-ORGANIZATION     0.8958    0.8966    0.8962      1064
     B-PERCENT     0.9429    0.9167    0.9296        36
      B-PERSON     0.9479    0.9353    0.9416       603
       B-PHONE     0.8333    0.9375    0.8824        16
        B-TIME     0.8316    0.8956    0.8624       182
         B-URL     1.0000    0.9545    0.9767        22
         B-ZIP     1.0000    1.0000    1.0000         6
        I-DATE     0.9811    0.9682    0.9746       913
       I-EMAIL     0.8889    1.0000    0.9412         8
         I-LAW     0.6125    0.7424    0.6712        66
         I-LEN     0.8545    0.9592    0.9038        49
    I-LOCATION     0.8940    0.8299    0.8608       935
       I-MONEY     0.9209    0.9831    0.9510       296
I-ORGANIZATION     0.8407    0.8071    0.8235      1327
     I-PERCENT     0.9245    0.9423    0.9333        52
      I-PERSON     0.9653    0.9761    0.9707      2220
       I-PHONE     1.0000    1.0000    1.0000        38
        I-TIME     0.9005    0.9515    0.9253       371
         I-URL     0.9839    0.9946    0.9892       368

     micro avg     0.9183    0.9149    0.9166     10048
```

## Reference (And Thank to)

- https://www.depends-on-the-definition.com/lstm-with-char-embeddings-for-ner/ for main idea code and overview model
- K.Wannaphong Phatthiyaphaibun (https://github.com/wannaphongcom/thai-ner) for dataset and the initial of Thai NER project
- K.Charin (https://github.com/cstorm125/thai2fit) for the word embbeding (Thai2Fit)
- Nils Reimers and Iryna Gurevych (https://arxiv.org/pdf/1707.06799.pdf) for Optimal Hyperparameters for Deep LSTM-Networks for Sequence Labeling Tasks
- Xuezhe Ma and Eduard Hovy (https://arxiv.org/pdf/1603.01354v5.pdf) for End-to-end Sequence Labeling via Bi-directional LSTM-CNNs-CRF
- Lampel et al. (https://arxiv.org/pdf/1603.01360.pdf) for Neural Architectures for Named Entity Recognition

## Citation

```
Suphanut Thattinaphanich (2019). Thai Named Entity Recognition with BiLSTM-CRF in Keras. May 16, 2019. See https://github.com/SuphanutN/Thai-NER-BiLSTM-WordCharEmbedding
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Contact

If you have any question, you can create an issure or send me a message to suphanut.tha@gmail.com
