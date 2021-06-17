# END_Assignment_5

#### Following types of data augmentation were supposed to be applied to the dataset
1. Back Translate
2. Random Insertion
3. Random Swap
4. Random Deletion

Before any augmentation this was the kind of distribution of the dataset

![full data without augmentation](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/full_data_wo_aug.png)

train list distribution before any kind of augmentation

![train no augmentation](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/train_list_wo_aug.png)

After Augmentaion this is the distribution for train set

![train data after augmentation](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/after_aug.png)

This is the distribution for test set without any augmentation

![test set without any augmentation](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/test_list.png)

Even with augmenting more of label 4 text, it still remains less compared to other classes. Only hoping that it still makes a difference to the models predictions.

#### The augmentation were of the following fraction

![class augmentation fractions](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/class_aug_fraction.PNG)


Without any kind of augmentation the model did not do well at all. It would overfit like crazy, it barely touched 33% with various hyper parameters listed as follows



Without any augmentation only a maximum of 33% was being achieved, apart from that, the model was overfitting crazy!!! Some of the following screenshots are proof of that.
We tried three creating models with RNN, LSTM, and GRU, using bidirectional, increasing dropout, increasing the number of layers, decreasing/increasing embedding dimensions. And also aking a bit of inspiration from best assignments, trying to understand what is to be done, we reached a maxinmum of 40.89% only.
The following screenshots are proof of that. And the training log for that run will be found ![here](https://github.com/kanchana-S/END_Assignment_5/blob/main/training_log/lstm_training_log) . With analysis done on the predictions, it was seen that label 4 was being predicted very less. Which lead to adding augmented texts with label 4 upto 80%.
Another thing i noticed was, smaller learning rates seem to work better than larger ones. The largest one i tried with was 0.5, the final learning rate was 0.0001.


The final model is a <b><b>two</b></b> layers LSTM, with dropout of <b>0.3</b>, embedding of <b>256</b> dimensions, and hidden nodes <b>50</b>. A rough diagram is as follows. 

![model](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/model.png)



It doesn't seem conventional to augment test data, but in my naivitiy, i augmented the complete dataset, and then split. I read later if this was valid, some say it is, some say it is not. It is for the instructor to decide now. Augmentation is done to help the model generalise, and increase records for any labels with less records, but only in training some say. But the argument is also that the train and test set should be similar for better accuracy, this is also apparently a common practice. But in any case the best predictions scores were achieved with augmenting the complete dataset method. The model even reached a validation accuracy of 45% multiple times for rnn and lstm. The training logs screenshots are as follows

with an lstm model

![lstm with full aug](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/LSTm_256_2_0001_200e_03d.PNG)

with an rnn model

![lstm with full aug](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/rnn_255_2_0001_200e_50h.PNG)


These model also did not overfit as crazy like as the previous models


Following is the output for predictions, they can also be found ![here](https://github.com/kanchana-S/END_Assignment_5/blob/main/training_log/output_25_samples) 

![predictions](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/example_25.PNG)

and false positives

![false positives](https://github.com/kanchana-S/END_Assignment_5/blob/main/images/false_positive.PNG)

### Way Forward
Another technique that could be used, but was't able to test out, is oversampling. Since label 4 seems to be smaller in number, and also not being predicted enough times, it could be oversampled in the training set to make up for less records and also to level up the training set for this label itself. One of the assignments also suggested to use to use pretrained embeddings like GloVe, which seems an interesting prospect, but unfortunately could not try it out.

Group Members

Sagar

Pushya
