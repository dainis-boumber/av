# av
authorship verification

some of the code got lost along the way of updates from one version of fastai to another (mostly GAN code).

Also training backward model is not any differnet - you just need to pass in the numericalized tokens backwards.

Starategy:

use forward trained and backward train Wiki-103

fine tune.

feed to forward RNN. forward QRNN, backward RNN, backward QRNN

meta-learner is used on outputs, it is (loosely) a NB-SVM model that assumes independce.

It also converts labels/entropies whichever to proper probabilities

You can output those, or make 0.5 threshold, or make mean threadhold if dataset is balanced.

Without meta-learner by just average results is around -+1% best reported to date. 

Then NB-SVM comes in :)
