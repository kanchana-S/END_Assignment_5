# END_Assignment_5

#### Following types of data augmentation were supposed to be applied to the dataset
1. Back Translate
2. Random Insertion
3. Random Swap
4. Random Deletion

Before any augmentation this was the kind of distribution of the dataset


After Augmentaion this is the distribution for train set

This is the distribution for test set without any augmentation


Even with augmenting more of label 4 text, the distribution does not change much, it reamins the same more or less.

We tried three creating models with RNN, LSTM, and GRU, using bidirectional, increasing dropout, increasing the number of layers, decreasing/increasing embedding dimensions. And also aking a bit of inspiration from best assignments, trying to understand what is to be done, we reached a maxinmum of 39.88% only. The following screenshots are proof of that. 
With analysis done on the predictions, it was seen that label 4 was being predicted very less. Which lead to augmenting text with label 4 upto 80%.

It doesn't seem conventional to augment test data, but in my naivitiy, i augmented the complete dataset, and then split. I read later if this was valid, some say it is, some say it is not. It is for the instructor to decide now. Augmentation is done to help the model generalise, and increase records for any labels with less records, but only in training some say. But the argument is also that the train and test set should be similar for better accuracy, this is also apparently a common practice. But in any case the best predictions scores were achieved with augmenting the complete dataset method. The model even reached a validation accuracy of 45% multiple times for rnn and lstm. The training logs screenshots are as follows



Following is the 
Another technique that could be used, but was't able to test out, is oversampling. Since label 4 seems to be smaller in number, and also not being predicted enough times, it could be oversampled in the training set to make up for less records and also to level up the training set for this label itself. One of the assignments also suggested to use to use pretrained embeddings like GloVe, which seems an interesting prospect, but unfortunately could not try it out.

Group Members
Sagar
Pushya